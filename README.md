# 🚀 DevOps Internship Assessment – Next.js Application Deployment

This repository contains my **DevOps Internship Assessment** project:  
A complete CI/CD workflow to containerize, build, and deploy a **Next.js web app** using **Docker**, **GitHub Actions**, and **Kubernetes (Minikube)**.

---

## 🎯 Objective

- Containerize a Next.js application using Docker  
- Automate build & image push to **GitHub Container Registry (GHCR)** using **GitHub Actions**  
- Deploy the image to **Minikube (Kubernetes)** using YAML manifests  
- Document the setup and usage clearly  

---

## 🧱 Project Architecture

```text
Next.js App → Docker → GitHub Actions → GHCR → Kubernetes (Minikube)
📁 Project Structure

nextjs-devops-assessment/
│
├── Dockerfile
├── package.json
├── next.config.js
├── pages/
│   └── index.js
├── public/
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
├── .github/
│   └── workflows/
│       └── ci-cd.yml
└── README.md

⚙️ Tech Stack
| Tool                      | Purpose               |
| ------------------------- | --------------------- |
| **Next.js**               | Web framework         |
| **Docker**                | Containerization      |
| **GitHub Actions**        | CI/CD automation      |
| **GHCR**                  | Docker image registry |
| **Kubernetes (Minikube)** | Orchestration         |
| **kubectl**               | K8s command-line tool |

🧩 1️⃣ Local Setup & Run

🧰 Prerequisites

Docker installed & running

Minikube installed

kubectl CLI configured

Git installed

🏗️ Clone the Repository

git clone https://github.com/vank1999/nextjs-devops-assessment.git
cd nextjs-devops-assessment

🐳 Build Docker Image

docker build -t nextjs-devops-assessment .

▶️ Run Container Locally

docker run -p 3000:3000 nextjs-devops-assessment

Visit → http://localhost:3000

🔄 2️⃣ GitHub Actions – CI/CD Pipeline

The workflow file is located at:

.github/workflows/ci-cd.yml

🧠 Workflow Overview

Triggers on push to main branch

Builds Docker image

Logs in to GHCR using ${{ secrets.GITHUB_TOKEN }}

Pushes the image to GHCR with :latest tag

🧾 Verify Image in GHCR

After a successful run:

Go to → https://github.com/users/<your-username>/packages

You’ll find your image

☸️ 3️⃣ Kubernetes Deployment (Minikube)

minikube start

📦 Apply Kubernetes Manifests

kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml

✅ Check Deployment

kubectl get pods
kubectl get svc

🌐 Access the App

minikube service nextjs-service

🧹 4️⃣ Cleanup Commands

kubectl delete -f k8s/deployment.yaml
kubectl delete -f k8s/service.yaml

Stop Minikube:

minikube stop


