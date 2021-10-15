# Sentiment-Analysis

1. Docker Hub images

  Frontend - https://hub.docker.com/repository/docker/rvimba/sentiment-analysis-frontend
  
  WebApp - https://hub.docker.com/repository/docker/rvimba/sentiment-analysis-webapp
  
  Logic - https://hub.docker.com/repository/docker/rvimba/sentiment-analysis-logic
  

2. Steps to get the application to work on GKE
3. 
In my local environment
- First I cloned the application code to my local machine. 
- Locally, I created the .jar file for the Java web application and built all three containers: frontend, web-app, and logic. 
- I pushed the images to my docker hub account (rvimba) 
- I pushed those images to the Google Container Registry, so I would be able to use them on Google Kubernetes Engine (GKE). 
- 
Google Kubernetes Engine
- In the Google console, I created a cloud shell where I did all my work to create a cluster and run the containers. 
- First, I created a cluster called 'sentiment-analysis' and enabled Kubectl 
- I cloned the 'k8s-mastery' repository to the cloud environment 
- I pulled my docker images that I uploaded to the container registry
- I created the deployments and LoadBalancer services for the frontend and web-app containers, and a service and deployment for the logic container.
- In order to enable the frontend to communicate with the web-app, I found the external IP of the web-app's LoadBalancer and adjusted the frontend's App.js file to communicate with this external IP address.
- I rebuild the frontend container, adjusted the frontend's deployment.yaml file, and applied the new deployment to the cluster.
- I used the external IP of the frontend LoadBalancer to access and test it from my browser. 
  
