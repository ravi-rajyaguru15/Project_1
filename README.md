# Multi-Tier Java App (Dockerized)

This project demonstrates a clean, containerized multi-tier Java web application using Docker Compose.

## Stack
- Java Web App (Tomcat)
- MySQL 8.0.33
- Memcached 1.6
- RabbitMQ 4.0
- Nginx 1.27

## Structure
- `web-app`: Built from source using Maven
- `mysql-db`: Official MySQL with init script
- `nginx-proxy`: Handles HTTP routing to app

## Coming Soon
- CI/CD pipeline
- Kubernetes orchestration
- Monitoring



-----------------------------------------------------------------------------------------------------------------

Perfect — here’s your first complete, professional-grade README.md for the project.

This is clean, personalized, and shows project ownership while still being technically grounded. You can paste this straight into your repo or tweak as needed.

# multi-tier-java-app-dockerized

**Containerization of a full-stack Java web application** with multiple dependent services using multi-stage Dockerfiles and Docker Compose.  
Includes **MySQL**, **RabbitMQ**, **Memcached**, **Tomcat**, and **Nginx** — deployed as a local isolated system on an EC2 instance.

---

## 🧱 Stack Overview

| Layer         | Technology               | Purpose                          |
|---------------|---------------------------|----------------------------------|
| App Runtime   | Tomcat 10 + JDK 21        | Serves WAR built via Maven       |
| Build Tool    | Maven 3.9.9               | Compiles Java source to WAR      |
| Reverse Proxy | Nginx 1.27                | Routes traffic to Tomcat         |
| Database      | MySQL 8.0.33              | Persistent data store            |
| Caching       | Memcached 1.6             | Application-level caching        |
| Messaging     | RabbitMQ 4.0-management   | Queue broker for async ops       |
| Orchestration | Docker Compose            | Manages multi-service lifecycle  |

---

## 🚀 How to Run (on EC2)

> Pre-requisites:
> - Docker & Docker Compose plugin installed
> - Ports 80, 8080, 3306, 5672, 15672, 11211 open in your EC2 Security Group

```bash
# 1. SSH into EC2
ssh -i docker-key.pem ubuntu@<your-ec2-public-ip>

# 2. Clone the repo
git clone https://github.com/your-account/multi-tier-java-app-dockerized.git
cd multi-tier-java-app-dockerized

# 3. Build & run containers
docker compose up --build -d

# 4. Visit the app (via Nginx)
http://<your-ec2-public-ip>

🧠 What I Did in This Project

Replaced all tutorial images with official builds and source-controlled services

Used a multi-stage Dockerfile to build and deploy a Java WAR inside Tomcat

Set up an Nginx reverse proxy container to route incoming traffic

Used .env for clean config separation

Structured the repo for clarity and modularity, not just functionality

🗂️ Project Structure
multi-tier-java-app-dockerized/
├── app/                   # Java app source + Dockerfile
├── mysql/                 # Custom MySQL init script
├── nginx/                 # Nginx reverse proxy config
├── .env                   # DB credentials and environment vars
├── docker-compose.yml     # Full stack orchestration
└── README.md

🛠️ Environment Variables

Defined in .env (auto-loaded by Docker Compose):

MYSQL_ROOT_PASSWORD=...
MYSQL_DATABASE=...
MYSQL_USER=...
MYSQL_PASSWORD=...

🌐 Exposed Ports
Service	Port
Web App (Nginx)	80
Tomcat (direct)	8080
MySQL	3306
RabbitMQ	5672
RabbitMQ UI	15672
Memcached	11211
🔭 Next Steps

This project is part of a 3-phase DevOps portfolio that builds progressively:

✅ Containerization (this repo)

🔄 Kubernetes Orchestration (coming next) — same app, deployed on AWS EKS

🔜 Infrastructure Automation + Monitoring — Terraform, CI/CD, Prometheus/Grafana

Each project builds on the last to demonstrate depth in:

Reproducible infrastructure

Scalable orchestration

Delivery pipelines

System observability

📸 Screenshots (Coming Soon)

You can add docker ps, running app UI, architecture diagrams, etc. here.

🧭 Final Notes

This is not a cloned tutorial — it’s a fully restructured project using only verified upstream components, built for clarity, reproducibility, and future scalability.