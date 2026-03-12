# Node DevOps Project

## Overview

This project demonstrates containerizing a Node.js application using Docker and Docker Compose.  
The application connects to MongoDB for database storage and Redis for caching.

The application runs on port **8090**.

---

## Technologies Used

- Node.js
- Docker
- Docker Compose
- MongoDB
- Redis

---

## Project Structure

node-devops-project
│
├── app.js
├── package.json
├── Dockerfile
├── docker-compose.yml
├── .env
├── .dockerignore
└── README.md

---

## Environment Variables

The application uses environment variables stored in the `.env` file.

Example:

PORT=8090  
MONGO_URI=mongodb://mongo:27017/devopsdb  
REDIS_HOST=redis  
REDIS_PORT=6379  

---

## How to Run the Project

### 1 Navigate to the project folder

cd node-devops-project

### 2 Build and start containers

docker compose up --build

### 3 Access the application

Open in browser:

http://54.81.228.81:8090

---

## Health Endpoint

http://54.81.228.81:8090/health

Example Response:

{
  "status": "UP",
  "mongo": "connected",
  "redis": "connected"
}

---

## Docker Services

The Docker Compose setup runs three services:

1. Node.js Application
2. MongoDB Database
3. Redis Cache

MongoDB data is persisted using Docker volumes.

---

## Optional Improvements Implemented

The following improvements were added:

- Docker container health checks
- Optimized Docker image using Node Alpine
- `.dockerignore` to reduce Docker image size
