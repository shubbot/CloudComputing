# ELL887 Cloud Computing - Assignment 1 (Containers)  
**Shubham Chandra**  
**M.Tech (Computer Technology)**  
**Entry Number: 2024EET2396**  

## Overview  
This assignment consists of three parts:  
1. *Modifying an existing web server container* (Nginx)  
2. *Creating and pushing a container* (Python program + POSTGRES database)  
3. *Deploying a web server in Kubernetes*  
---
## Part 1: Modifying an Existing Web Server Container

### Objective
This part modifies an Nginx container to serve a custom webpage at http://localhost/ELL887.

### Files Provided:
- Dockerfile (to create a custom Nginx container)
- index.html (to display the required message)

### Steps to Run:
1. *Build the container:*
   ```sh
   docker build -t modified-nginx .

2. **Run the container:**
   ```sh
   docker run -d -p 80:80 modified-nginx
<img width="845" alt="1 1" src="https://github.com/user-attachments/assets/0573f2d9-1ea1-43a3-9d79-02bfb8851271" />

3. *Verify the output:*
   ```sh
   [htttp://localhost/ELL887](http://localhost/ELL887)

   OUTPUT: "Hello world! I am Shubham Chandra".
<img width="959" alt="1 2" src="https://github.com/user-attachments/assets/afa7c3b1-9118-4bd3-ba49-359606a58fbd" />

---

## Part 2: Creating and Pushing a Container

### Objective
This part containerizes a Python program that prints "Hello world!! I am Shubham Chandra" and includes a postgres database.

### Files Provided:
- `Dockerfile` (to create a custom Nginx container)
- `docker-compose.yaml` (to include a POSTGRES database)
- `index.html` (to display the required message)

### Steps to Run:
A. **Run the Python program container**
1. **Build the Python container:**
   ```sh
   docker build -t my-application .

2. *Run the container:*
   ```sh
   docker run my-application

3. **Verify the output:**
   ```sh
   OUTPUT: "Hello world!! I am Shubham Chandra".
<img width="959" alt="2 2" src="https://github.com/user-attachments/assets/4eef4ecb-e54b-41e6-820e-c6caf41d4520" />


B. *Start the Database using Docker Compose*
1. *Run the services(Python ap + POSTGRES database)*
   
   ```sh
    docker-compose up

2. **Use different terminal to use POSTGRES**
   ```sh
     docker run -d -p 5432:5432 -e POSTGRES_USER=v -e POSTGRES_PASSWORD=password -e POSTGRES_DB= shubbot/ell887:db

3. *Repositories pull command*
   ```sh
    docker pull shubbot/ell887:app 
    docker pull shubbot/ell887:db 
<img width="955" alt="docker_desktop" src="https://github.com/user-attachments/assets/ba19537a-4b9d-4155-962f-e420580677d3" />


For connecting the py and postgres, I have used the left side docker-compose file and submitted the right side image_ docker-compose file in which I have updated the image as docker repositories.

<img width="431" alt="prev" src="https://github.com/user-attachments/assets/697d7fd4-5dc6-414d-98b3-26ceac59f3da" />
<img width="412" alt="image" src="https://github.com/user-attachments/assets/9520ce24-6480-42fd-bf5a-40071777d54c" />


4. **To verify the output**
   ```sh
   docker compose up
<img width="959" alt="5" src="https://github.com/user-attachments/assets/05391f2d-6089-44db-b71b-9cd512c19014" />
<img width="959" alt="8_final" src="https://github.com/user-attachments/assets/b616eba6-c090-499e-97e8-9c382f411737" />


---

## Part 3: Modifying an Existing Web Server Container

### Objective
Deploy a web server in a Kubernetes cluster using Minikube. web server runs on port 30001

### Files Provided:
- deployment.yaml (K8s Deployment & service for the web server)

### Steps to Run:
1. *Apply the Kubernetes configuration using:*
   ```sh
   kubectl apply -f deployment.yaml

2. **check the running pods using:**
   ```sh
   kubectl get pods
   
3. *check the service pods using (wait until webserver pod is in running state the use below cmd):*
   ```sh
   minikube service webserver-service

<img width="959" alt="image" src="https://github.com/user-attachments/assets/21823081-6f8d-452a-9c2b-ee1e4b3b9a47" />


4. **Access the web server using:**
   ```sh
   [http://127.0.0.1:60294](http://127.0.0.1:60294)

   OUTPUT: nginx web page.

<img width="959" alt="image" src="https://github.com/user-attachments/assets/35078361-0e0d-4345-afa6-1168a923d900" />
