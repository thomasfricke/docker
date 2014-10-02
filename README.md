docker
======

Minimal Dockerfile with configuration for
- supervisord
- sshd
- login by (my :-) public key


To create a docker image run

docker build -t example/base:first .

To create a container run

docker run  --privileged -h base.example.com  -p 22 -t example/base:first

Find the docker container id by docker ps and get find the IP address by

docker inspect -format '{{ .NetworkSettings.IPAddress }}' ${CONTAINERID}

Now you can login with 

ssh root@${IPADDRESS}


