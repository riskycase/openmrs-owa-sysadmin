<img src="https://cloud.githubusercontent.com/assets/668093/12567089/0ac42774-c372-11e5-97eb-00baf0fccc37.jpg" alt="OpenMRS"/>

# System Administration Open Web App  - GSoC 2017 Project

This repository contains the Open Web App developed for System Administration module [MetaData Management in Admin UI Project](https://wiki.openmrs.org/display/projects/More+Metadata+Management+in+AdminUI).

Final report about the Project : [More Metadata Management in AdminUI - GSoC 2017 Project](https://wiki.openmrs.org/display/projects/More+Metadata+Management+in+AdminUI+-+GSoC+2017+Project)

> System Administration modules functionality implemented as an OWA for OpenMRS

For further documentation about OpenMRS Open Web Apps see [the wiki page](https://wiki.openmrs.org/display/docs/Open+Web+Apps+Module).

## Project

In the More Meta data Management in AdminUI project, We focused on this following functionalities,
1. Manage modules
2. System Information
3. Manage Scheduler

### The Project goals
1. Migrate the legacy functionalities to the modern open web apps
2. Increase the user experience and feasibility of the legacy functionalities
3. Extend the usage of the legacy functionalities with REST APIs
4. Extend the administrative features using existing functionalities
5. Improve the problems which are identified in the legacy UI modal

### OWA Development Progress

Under Development Stage, Completed Functionalities are
 1. Manage Modules
 2. System Information
 3. Manage Scheduler

## Development

#### Manage Modules
1. Implement all functionalities in the Manage Module to Open Web App.
2. List all the installed Modules and allow admin users to control the Modules using Start, Stop and Unload actions.
3. View the Installed module’s details with required Module’s.
4. Upload Modules(.omod File) to the OpenMRS Server and Start uploaded Module
5. Search the modules from OpenMRS Modules Repo and Install to the OpenMRS Server
6. Check installed modules updates
7. Start All modules functionalities

#### System Information
1. Provide all the information to the user
2. Categorized and implement the Information page.

#### Manage Scheduler
1. Manage the tasks in the system 
2. Add/Modify/Unload the task definitions
3. Scheduler/Shoutdown/ReSchedule the existing tasks

### Setup OpenMRS server

You will need JDK 1.7, maven and OpenMRS SDK. Please refer to [the wiki page] (https://wiki.openmrs.org/display/docs/OpenMRS+SDK#OpenMRSSDK-Installation) for installation instructions.

You need to setup a server (first time only) as follows:
You should install and run the OpenWebApp Module and REST WebServices module to run this System Admin Open Web App

````
mvn openmrs-sdk:setup-platform -DserverId=adminmodule
mvn openmrs-sdk:install -DartifactId=owa -Dversion=1.7-SNAPSHOT -DserverId=adminmodule
mvn openmrs-sdk:install -DartifactId=webservices.rest -Dversion=2.21 -DserverId=adminmodule
mvn openmrs-sdk:install -DartifactId=uiframework -Dversion=3.6 -DserverId=adminmodule
mvn openmrs-sdk:install -DartifactId=uicommons -Dversion=1.7 -DserverId=adminmodule
````

Now you can run the server:
````
mvn openmrs-sdk:run -DserverId=adminmodule
````
Once it says "Started Jetty Server", visit http://localhost:8080/openmrs in your browser.

### Production Build

You will need NodeJS 4+ installed to do this. See the install instructions [here](https://nodejs.org/en/download/package-manager/).

Once you have NodeJS installed, you need to install Gulp and Bower (first time only) as follows:
````
npm install -g gulp bower
````

Install the dependencies (first time only):

```
npm install && bower install
```

Build the distributable using [Gulp](http://gulpjs.com/) as follows:

````
gulp
````

This will create a file called `ManageModule.zip` file in the `dist` directory, which can be uploaded to the OpenMRS Open Web Apps module.

## License

[MPL 2.0 w/ HD](http://openmrs.org/license/) © [OpenMRS Inc.](http://www.openmrs.org/)
