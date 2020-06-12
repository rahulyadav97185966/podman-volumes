# podman-volumes

mkdir /mydata : Create Directory using this command in which the data of the container will be stored

podman run -v /mydata:/var/lib/mysql:Z -e MYSQL_ROOT_PASSWORD=redhat -d docker.io/mysql:5.6  : using this command we run the mysql container in backend using -d (detach ) option , Z is for pemissive the SElinux (Security-Enhanced Linux) policies that allows user to create and use file and folders . (.var/lib/mysql) this directory we can see using #docker inspect <image_id> this command in this      "Volumes": {
                "/var/lib/mysql": {}
            }
            this section conatines th e path

podman ps : using this command we will see the running containers.

podman exec -it 49 bash :using this command we can access teh running container
  --> mysql -uroot -predhat :using this command we can enter into the mysql shell

Now exit from the contanier and go to mydata Directory (cd /mydata) and using (ls -Z or ls) we can see the data present there 
