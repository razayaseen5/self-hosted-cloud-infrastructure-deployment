# Self-Hosted Cloud Infrastructure & Website Deployment

A production-grade, self-hosted server architecture deployed on an Oracle Cloud Ubuntu VPS. This repository contains the Docker Compose configurations and routing logic used to securely host multi-container web and automation workloads for a private production environment.

## Architecture Overview

This infrastructure utilizes a reverse proxy to handle external DNS routing, SSL termination, and secure internal container communication. 

* **Hosting:** Oracle Cloud Infrastructure (Always Free Tier Ubuntu VPS)
* **Containerization:** Docker & Docker Compose
* **Traffic Routing & SSL:** Nginx Proxy Manager, Cloudflare DNS (Full Strict Mode)
* **Workloads:** 
  * WordPress (CMS) + MySQL 8.0 (Database)
  * n8n (Workflow Automation Engine)

## Security & Network Design

* **Internal Docker Networks:** Services communicate over isolated custom bridge networks (`proxied`) to prevent unauthorized port exposure.
* **Environment Variables:** Credentials and database keys are injected dynamically via `.env` files (see `.env.example` for the structure).
* **HTTPS/TLS:** Automated Let's Encrypt certificates managed through Nginx Proxy Manager, combined with Cloudflare's proxy shield to prevent direct IP access.

## Author
**Raza Yaseen**  
Head of Business Operations, Tech Projects & Strategy