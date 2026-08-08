# ☕ Starbucks Clone – End-to-End DevSecOps Project

<p align="center">

## 🚀 Starbucks Clone Application Deployment using DevSecOps, Kubernetes & Monitoring

**GitHub → Terraform → AWS EC2 → Jenkins → SonarQube → Docker → Trivy → Docker Registry → Kubernetes → OWASP ZAP → Route 53 → Prometheus → Grafana → Email Alerts**

</p>

---

# 📌 Project Title

## Starbucks Clone – End-to-End DevSecOps CI/CD Pipeline with Kubernetes, Security & Monitoring

---

# 📖 Project Overview

This project demonstrates the complete **DevSecOps lifecycle** of deploying a
Starbucks Clone web application on AWS.

The source code is maintained in **GitHub** and infrastructure is provisioned
using **Terraform** on **AWS EC2**.

**Jenkins** automates the CI/CD pipeline with **SonarQube** for code quality,
**Docker** for containerization, **Trivy** for container vulnerability
scanning, and **OWASP ZAP** for application security testing.

The application is deployed on **Kubernetes**, exposed through **DNS**, and
monitored using **Prometheus and Grafana**.

Email alerts are configured for important CI/CD, security, and monitoring
events.

---

# 🏗️ Project Architecture

```text
                                   DEVELOPER
                                       │
                                       ▼
                              ┌─────────────────┐
                              │     GitHub      │
                              │   Source Code   │
                              └────────┬────────┘
                                       │
                                  Webhook / Push
                                       │
                                       ▼
                              ┌─────────────────┐
                              │     Jenkins     │
                              │     CI / CD     │
                              └────────┬────────┘
                                       │
                                       ▼
                              ┌─────────────────┐
                              │      Build      │
                              │   Application   │
                              └────────┬────────┘
                                       │
                                       ▼
                              ┌─────────────────┐
                              │    SonarQube    │
                              │  Code Quality   │
                              └────────┬────────┘
                                       │
                                  Quality Gate
                                       │
                                       ▼
                              ┌─────────────────┐
                              │      Docker     │
                              │   Build Image   │
                              └────────┬────────┘
                                       │
                                       ▼
                              ┌─────────────────┐
                              │      Trivy      │
                              │ Security Scan   │
                              └────────┬────────┘
                                       │
                                Scan Successful
                                       │
                                       ▼
                              ┌─────────────────┐
                              │ Docker Registry │
                              │    / ECR        │
                              └────────┬────────┘
                                       │
                                       ▼
                              ┌─────────────────┐
                              │   Kubernetes    │
                              │     Cluster     │
                              └────────┬────────┘
                                       │
                        ┌──────────────┼──────────────┐
                        │              │              │
                        ▼              ▼              ▼
                 ┌────────────┐ ┌────────────┐ ┌────────────┐
                 │ Starbucks  │ │ Prometheus │ │  Grafana   │
                 │ Application│ │ Monitoring │ │ Dashboard  │
                 └──────┬─────┘ └──────┬─────┘ └──────┬─────┘
                        │              │              │
                        │              └──────┬───────┘
                        │                     │
                        ▼                     ▼
                 ┌────────────┐       ┌────────────┐
                 │  Route 53  │       │ Email Alert│
                 │    DNS     │       │Notification│
                 └──────┬─────┘       └────────────┘
                        │
                        ▼
                      USERS

                         APPLICATION SECURITY
                                  │
                                  ▼
                          ┌─────────────┐
                          │  OWASP ZAP  │
                          │     DAST    │
                          └─────────────┘
