# Audio-Visual-Cooking-Assistant
Hello!
This repository will enable you to have a fully functional Audio-Visual-Cooking-Assistant. 
The readme guides you through the main steps of setting it up.

!important!
It is really recommended to be familiar with setting up enviroments on docker-compose and have it installed:
https://docs.docker.com/compose/
It is also highly recommended to read the rhasspy documentation:
https://rhasspy.readthedocs.io/en/latest/

The given prototype tool can also easily be customized. For this you might check: 
1. https://svelte.dev/
2. https://nodejs.org/en/
3. https://mqtt.org/


There a many use cases to use the prototype as it can be adjusted to visualize every audio-visual device that has a GUI based on basically any kind of common screen. You can set it up locally or on a public server. For local use check out the rhasspy documentation. For setting it up on a public server We won´t recommend but show you the way we did it. The following shows the architecture for better understanding:
![prototype_architecture_backup2](https://user-images.githubusercontent.com/82209800/121739527-089cdf80-cafc-11eb-80fc-a82fb6144ae2.png)



Feel free to use the Server that fits you best.

We used for the rhasspy server:
EC2 by AWS (https://aws.amazon.com/de/)

For the Svelte frontend:
Elastic Beanstalk by AWS (https://aws.amazon.com/de/)


1.We provide a production-ready docker-compose file within our repository to build and run the prototype.
But at first you need to run install a local server instance with rhasspy running:
https://rhasspy.readthedocs.io/en/latest/

Cutomizing:
Just add the content of our rhasspy-config.yml to the advanced section on your local rhasspy server.![Screen Shot 2021-06-11 at 21 25 53](https://user-images.githubusercontent.com/82209800/121739258-a643df00-cafb-11eb-94c5-bb3fc4d2022a.png)


2. If rhasspy is setup you´re good to go and you can start building the middleware backend and frontend by utilizing the docker-compose file.
but before you have to check the rhasspy server ip:
server>source>index.js

change following lines with your configuration:
const PORT = process.env.PORT || 3000;
const HOST = process.env.HOST || '0.0.0.0';
const MQTTHOST = process.env.MQTTHOST || '3.94.213.112';
const RHASSPY_PORT = process.env.RHASSPY_PORT || 12183;

navigate into the folder and simply run:
$ docker-compose build
$ docker up







