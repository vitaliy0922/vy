Eclipse Che is both a cloud IDE and an SDK for creating a custom cloud IDE by packaging extensions you author into an assembly. Che can be used as a desktop IDE, embedded IDE, or a hosted IDE.

Che contains:
* A cloud IDE
* A set of extensions for many programming languages, source code systems, builders and runners
* A kernel for loading extensions authored as plug-ins
* Developer tooling for building and and assembling plug-ins to create new IDEs
* A set of platform APIs for developer microservices (e.g., 'build project' or 'search workspace')
* A CLI for interacting with platform APIs
* An Eclipse plug-in for editing, building and running Che projects from within Eclipse


![Eclipse Che](https://codenvy.com/images/image-editor@1x.png "Eclipse Che")

The IDE is a browser application that is generated by compiling extensions into JavaScript. Extensions can invoke server-side APIs that run within the Che kernel. The kernel is a servlet-based framework that loads and manages extensions. The kernel can be run in any servlet container with a default bundling of Tomcat.

Che can be installed on any OS that supports Java 1.7 - desktop, server or cloud, and Maven 3.1.1 or higher. It has been tested on Ubuntu, Linux, MacOS and Windows. Java, GWT, GIN and JavaScript are the core technologies used to build Che.

### License
Che is open sourced under the Eclipse Public License 1.0.

### Clone the repository

```sh
git clone https://github.com/codenvy/che.git
```
If master is unstable, checkout the latest released version.

### Build and run Che
```sh
cd che
mvn clean install
./che.sh [ start | stop ]
```

This builds and runs an assembly with Java and extensions required for building plug-ins. You can create other assemblies that include your extensions or the complete set provided with Che.

Che will be available at ```localhost:8080```

### Che sub-projects:
* **che-plugins**:             [Language & tooling extensions] (http://github.com/codenvy/che-plugins)
* **che-core**:                [Core components] (http://github.com/codenvy/che-core)
* **che-depmgt**:              [Maven dependency management POM] (http://github.com/codenvy/che-depmgt)
* **che-parent**:              [Maven parent POM] (http://github.com/codenvy/che-parent)

### Other projects that are part of Eclispe Che
* **CLI**:                     [CLI for interacting with Che remotely] (http://github.com/codenvy/cli)
* **Eclipse Plug-In**:         [An Eclipse plug-in for running Che projects] (http://github.com/codenvy/eclipse-plugin)

### AngularJS plugin configuration
This plugin requires npm, Yeoman, Bower and Grunt to be installed.

* npm setup guide : https://github.com/npm/npm
npm is bundled with nodejs which can be downloaded from: http://nodejs.org/download/

* Yeoman (and bower / Grunt dependencies can be installed with: npm install -g yo)
   more details on http://yeoman.io/gettingstarted.html

### Add your extensions to Che
1. Create, build and compile a Che extension into a Java JAR file. [Tutorial is here] (http://docs.codenvy.com/che/). You can create extension JARs within Che or your favorite IDE. Build extensions in Eclipse gives you super dev mode for Eclipse, which makes incremental compilation fast.

2. Copy the extension's JAR file to ```/assembly-sdk/target/tomcat-ide/ext``` directory of Che.  

3. Execute ```$ ./extInstall.sh``` script. Che will be re-compiled with your extension. This will take a few minutes.

4. Restart Che.

### Help us

**Contribute:**: We accept pull requests, so if you feel like contributing to the project, you are definitely welcome to do so.

**Report Bugs:** You can report bugs and contribute [che-dev@eclipse.org](email:che-dev@eclipse.org). 

### Documentation & Tutorials
* **Che Getting Started:** [http://eclipseche.org/] (http://eclipseche.org/)
* **Che Docs:** [http://eclipseche.org/docs] (http://eclipseche.org/docs)
* **Che Extension Authoring:** [http://eclipseche.org/docs/extension-development/] (http://eclipseche.org/docs/extension-development/)


### Contact Information
* **Che Mailing List:** [che-dev@eclipse.org](email:che-dev@eclipse.org)
* **Website:** [eclipseche.org](https://eclipseche.org)
* **Eclipse Che Project Page:** [https://projects.eclipse.org/projects/technology.che](https://projects.eclipse.org/projects/technology.che)
