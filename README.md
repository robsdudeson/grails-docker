**Grails environment**

This repository objective is to allow users to test and run their
Grails applications without needing to install Grails in their own
machines. The port 8080 (Grails default port) is open, and can be linked
to a local port in order to access the app.
In order to link the port, you can you the following command (it
connects your local port 8888 to the port 8080 in the container)
**docker run -p 8888:8080 -it robsdudeson/grails /bin/bash**

To automatically remove the container after using it, you only need to
add the --rm parameter:
**docker run -p 8888:8080 -it --rm robsdudeson/grails /bin/bash**

If you want to name your container, you this command:
**docker run -p 8888:8080 -it --name <container_name> robsdudeson/grails /bin/bash**

The tags follow this pattern::
* **robsdudeson/grails:latest** - Most recent Grails version with Debian.
* **robsdudeson/grails:X.X.X** - Grails specific version with Debian. In
 this repository, the minimum Grails version is 3.2.8
* **vaidegrails/grails:X.X.X-alpine** - Grails specific version with
Alpine Linux. In this repository, the minimum Grails version is 3.2.8

These are the configuration of the container:

* Operational System:
  - Debian (testing) or Alpine 3.5
* User:
  - developer
* SDKs:
  - OpenJDK 8
  - Grails 3.2.8
  - Gradle 3.4.1
* Grails Version Management:
  - SDKMAN!
* Version System:
  - git
* Auxiliary Tools:
  - gitg
  - curl
  - nano
  - unzip
* Exposed ports:
  - 8080 (Grails default port)
  - 5005 (Debug port)

The Docker Hub repository can be found at: https://hub.docker.com/r/robsdudeson/grails/

If you want to run this image, you can use the script run_image.sh:
**scripts/run_image.sh**

To run the Alpine version:
**scripts/run_image_alpine.sh**

If you want to build the image:
**scripts/build_image.sh**

If you want to build the Alpine image:
**scripts/build_image_alpine.sh**
