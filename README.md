#docker-compose-maven-mysql
It is a project to run multiple containers(Java and MySQL) Docker application. Java application running on a container will connect to MySQL database running on another container.

## sample-maven-app
A maven project with only one class that tries to connect to MySQL database.
Dockerfile present in the app 
    - Uses ubuntu 18.04 as a base image.
    - Installs Java 11 and sets environment path
    - Installs maven
    - Builds project and generate an executable jar file with the help of maven assembly plugin
    - Then it executes java -jar command to run jar sample-maven-app jar file

## docker-compose.yml
Docker compose file defines mysql and maven-app services.
    1. `docker-compose build` builds/rebuilds images for mysql and sample-maven-app
    2. `docker-compose up -d` to bring up application. Docker compose creates a network which can be used by containers to communicate with each other.
    3. `docker-compose down` to bring down the app