# Nexus

### [Nexus Installation Process](https://github.com/learn-with-devops/devops/blob/master/Nexus/Nexus_Installation.md)

### Nexus Configuration with Docker 

         Create a file under /etc/docker folder like below
         
         vi /etc/docker/daemon.json
         
            {
              "insecure-registries": [
                "18.216.203.67:8088"
              ],
              "disable-legacy-registry": true
            }
            
### Try to login to the Nexus repository from your docker server

      docker log -u <username> -p <password> <nexusservername>:<repo port>
            
### Docker Image Pulling and pushing to Nexus repo

      # Please Pull one basic/required image to your server
      docker pull alpine

      Note : 

      # If you want download an Image from Nexus DTR directly then follow like below
      docker pull <nexus-hostname>:<repository-port>/<image>

      # Rename the tag for that image
      docker tag alpine <nexus-server-ip>:<repo-port>/<imag_name>
      ex: 
      docker tag alpine 18.216.203.67:8088/alpine:latest

      # Finally push your image to Docker registory
      docker push <image_name>

  
