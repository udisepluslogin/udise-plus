# 📊 UDISE Plus - Unified District Information System for Education Plus

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.11+-green.svg)](https://www.python.org/)
[![React](https://img.shields.io/badge/React-18.2+-blue.svg)](https://reactjs.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-15.2-blue.svg)](https://www.postgresql.org/)
[![Azure](https://img.shields.io/badge/Cloud-Azure-0078D4.svg)](https://azure.microsoft.com/)
[![Contributors](https://img.shields.io/github/contributors/ministry-of-education/udise-plus-platform.svg)](https://github.com/ministry-of-education/udise-plus-platform/graphs/contributors)
[![Stars](https://img.shields.io/github/stars/ministry-of-education/udise-plus-platform.svg)](https://github.com/ministry-of-education/udise-plus-platform/stargazers)
[![Issues](https://img.shields.io/github/issues/ministry-of-education/udise-plus-platform.svg)](https://github.com/ministry-of-education/udise-plus-platform/issues)

> Official repository of UDISE Plus - India's flagship educational data management platform

**Managed by:** Department of School Education & Literacy, Ministry of Education, Government of India

---

## 🌟 Overview

UDISE Plus (Unified District Information System for Education Plus) is **Asia's largest education database** and the world's **second-most comprehensive school information system** (after China). It provides real-time tracking and management of:

- **🎓 26.52 Crore Students** (265.2 million) from pre-primary to higher secondary
- **👨‍🏫 95.07 Lakh Teachers** (9.5 million educators) across all levels
- **🏫 14.89 Lakh Schools** (1.489 million institutions) - government, aided, and private
- **📍 766 Districts** covering all 36 states and union territories of India

**🔗 Portal Access:** [https://udisepluslogin.com/](https://udisepluslogin.com/)

---

## 🎯 Mission

To create a comprehensive, real-time, and accurate database of every student, teacher, and school in India, enabling:

- Evidence-based education policy formulation
- Transparent resource allocation
- Early dropout prevention through data analytics
- Efficient scholarship disbursement via Direct Benefit Transfer (DBT)
- Infrastructure gap identification and planning
- Teacher deployment optimization

---

## 📊 Key Statistics (2024-25)

| Metric | Value | Description |
|--------|-------|-------------|
| **Total Students** | 26,52,00,000 | Students enrolled across all levels |
| **Total Teachers** | 95,07,000 | Educators managing classrooms |
| **Total Schools** | 14,89,115 | Educational institutions nationwide |
| **Districts Covered** | 766 | 100% geographic coverage |
| **Data Points Processed** | 2.5 Billion/year | Annual data processing volume |
| **Concurrent Users** | 247,000 (peak) | Maximum simultaneous users |
| **Data Accuracy** | 99.3% | Post-validation accuracy rate |
| **System Uptime** | 99.9% | Annual availability guarantee |
| **Scholarship Disbursed** | ₹75,000 Crore | Annual DBT amount |
| **API Requests** | 85,000/sec (peak) | Maximum request handling capacity |

---

## 🏗️ Architecture

### System Design

┌─────────────────────────────────────────────────────────────┐
│ Frontend Layer │
│ React 18.2 • Redux Toolkit • Material-UI • TypeScript │
└──────────────────────┬──────────────────────────────────────┘
│
┌──────────────────────▼──────────────────────────────────────┐
│ API Gateway Layer │
│ Kong Gateway • Nginx • JWT Auth • Rate Limiting │
└──────────────────────┬──────────────────────────────────────┘
│
┌──────────────────────▼──────────────────────────────────────┐
│ Microservices Layer │
│ │
│ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ │
│ │ Student │ │ Teacher │ │ School │ │
│ │ Service │ │ Service │ │ Service │ │
│ │ (FastAPI) │ │ (FastAPI) │ │ (FastAPI) │ │
│ └──────────────┘ └──────────────┘ └──────────────┘ │
│ │
│ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ │
│ │ Analytics │ │ Scholarship │ │ Attendance │ │
│ │ Service │ │ Service │ │ Service │ │
│ │ (Python) │ │ (Python) │ │ (Node.js) │ │
│ └──────────────┘ └──────────────┘ └──────────────┘ │
└──────────────────────┬──────────────────────────────────────┘
│
┌──────────────────────▼──────────────────────────────────────┐
│ Data Layer │
│ │
│ ┌──────────────────────────────────────────────────────┐ │
│ │ PostgreSQL 15.2 (Primary Database) │ │
│ │ State-based Sharding (36 shards) │ │
│ │ Master-Slave Replication │ │
│ └──────────────────────────────────────────────────────┘ │
│ │
│ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ │
│ │ Redis │ │ MongoDB │ │Elasticsearch │ │
│ │ Cluster │ │ 6.0 │ │ 8.5 │ │
│ │ (Cache) │ │(Unstructured)│ │ (Search) │ │
│ └──────────────┘ └──────────────┘ └──────────────┘ │
└──────────────────────┬──────────────────────────────────────┘
│
┌──────────────────────▼──────────────────────────────────────┐
│ Cloud Infrastructure (Azure) │
│ AKS • Blob Storage • Azure Monitor • Front Door CDN │
└─────────────────────────────────────────────────────────────┘

text


### Technology Stack

**Frontend:**
- React 18.2 with TypeScript
- Redux Toolkit for state management
- Material-UI component library
- Vite build tool
- Progressive Web App (PWA) capabilities

**Backend:**
- **Primary:** Python 3.11 with FastAPI framework
- **Worker Services:** Node.js 18 LTS
- **Batch Processing:** Apache Airflow
- **Real-time Processing:** Apache Kafka + Apache Flink
- **Caching:** Redis Cluster (6-node)

**Database:**
- **Primary:** PostgreSQL 15.2 with state-based sharding
- **Data Warehouse:** Apache Druid
- **Document Store:** MongoDB 6.0
- **Search Engine:** Elasticsearch 8.5
- **Backup:** Azure Blob Storage + Glacier

**Cloud & DevOps:**
- **Cloud Provider:** Microsoft Azure Government Cloud
- **Orchestration:** Kubernetes (AKS)
- **CI/CD:** GitHub Actions + Azure DevOps
- **Monitoring:** Grafana + Prometheus + Azure Monitor
- **Logging:** ELK Stack (Elasticsearch, Logstash, Kibana)

**Security:**
- SSL/TLS 256-bit encryption
- OAuth 2.0 + JWT authentication
- HMAC-SHA256 for sensitive data
- Azure Web Application Firewall (WAF)
- ISO 27001 certified infrastructure

---

## 🚀 Getting Started

### Prerequisites

```bash
# System Requirements
- Node.js 18+ LTS
- Python 3.11+
- PostgreSQL 15.2+
- Redis 7.0+
- Docker 24.0+ & Docker Compose
- Git 2.40+

# Minimum Hardware
- CPU: 4 cores
- RAM: 8GB
- Storage: 20GB free space
