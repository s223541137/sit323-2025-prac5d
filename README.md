# SIT323-2025-Prac5D: Publishing Microservice to the Cloud (Task 5.2D)

## 🔹 Microservice Overview

This project contains a Node.js Express-based microservice designed to perform basic arithmetic operations including addition, subtraction, multiplication, and division.  
The microservice is containerized using Docker and deployed to a cloud-based container registry as required for SIT323 Task 5.2D.

---

## 🔹 Technologies Used

- Node.js
- Express.js
- Docker
- Docker Hub (alternative cloud registry)

---

## 🔹 Deployment Instructions

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/s223541137/sit323-2025-prac5d.git
cd sit323-2025-prac5d
2️⃣ Docker Build
Build the Docker image locally:

docker build -t s223541137/task-5.2d:v1 .
3️⃣ Docker Login
Authenticate to Docker Hub:

docker login
Enter your Docker Hub username (s223541137) and password when prompted.

4️⃣ Docker Push
Push the Docker image to Docker Hub:

docker push s223541137/task-5.2d:v1
✅ Image is publicly available at:
https://hub.docker.com/r/s223541137/task-5.2d

5️⃣ Docker Run (from Published Image)
Pull and run the containerized microservice:

docker pull s223541137/task-5.2d:v1
docker run -p 3000:3000 s223541137/task-5.2d:v1
Access the service at:

http://localhost:3000
Example usage:

http://localhost:3000/add?num1=5&num2=3
🔹 Microservice API Endpoints


Method	Endpoint	Query Parameters	Example Call
GET	/add	num1, num2	/add?num1=5&num2=3
GET	/subtract	num1, num2	/subtract?num1=10&num2=4
GET	/multiply	num1, num2	/multiply?num1=7&num2=6
GET	/divide	num1, num2	/divide?num1=20&num2=5
🔹 Important Note on Deployment

As per SIT323 Task 5.2D instructions, the microservice was intended to be deployed to Google Cloud Container Registry (GCR).
However, due to limited permissions associated with the Deakin University provided Google Cloud project (Project ID: 842012414213), it was not possible to enable the Artifact Registry API. Without this API, Google Cloud blocks the ability to push container images.
Despite multiple attempts, the "denied: Artifact Registry API has not been used in project" error persisted, and Deakin students do not have the administrative privileges required to resolve this issue independently.
Therefore, to meet the task requirements of cloud-based image publishing, Docker Hub was used as an alternative.
All required steps including:
Containerizing the microservice
Authenticating with a registry
Pushing the image to a cloud registry
Running the microservice from the published image
have been fully completed according to the original instructions.
