# Pet Passport Agent — AI Travel Assistant for Pets

An intelligent AI agent built using **Google Agent Development Kit (ADK)** and **Model Context Protocol (MCP)** that helps pet owners explore pet-friendly locations, discover nearby services, and analyze pet-related data through connected tools.

This project demonstrates how modern AI agents go beyond simple chatbot interactions by combining **LLM reasoning**, **external tool usage**, and **real-world data access** through MCP servers.

---

## Project Overview

Planning travel with pets often requires searching multiple platforms for:

* Pet-friendly places
* Nearby veterinary services
* Location information
* Breed-related insights
* Regional pet data

The **Pet Passport Agent** solves this by acting as an AI assistant that can understand user requests, decide which tools are required, call external services, and return useful answers.

Instead of manually searching different systems, users interact with one intelligent agent.

---

# Architecture

The project follows an agentic architecture where the model acts as the reasoning layer and external systems are connected through MCP tools.

```text
User Query
     |
     v
Google ADK Agent
     |
     v
Gemini 2.5 Flash
(Reasoning Layer)
     |
     |
     +----------------------+
     |                      |
     v                      v
Google Maps MCP        BigQuery MCP
Tool Server            Tool Server
     |                      |
     v                      v
Places Data            NYC Dog Dataset
     |
     v
Final AI Response
```

---

# How The Agent Works

The agent contains three core components.

---

## 1. Reasoning Engine

Powered by **Gemini 2.5 Flash**

Responsibilities:

* Understand user intent
* Decide required actions
* Select appropriate MCP tools
* Generate natural language responses

---

## 2. Model Context Protocol (MCP) Layer

MCP enables the agent to communicate with external tools and services using a standardized protocol.

The project integrates multiple MCP servers.

---

## Google Maps MCP Toolset

Provides location intelligence capabilities.

Features:

* Search locations
* Find pet-related services
* Retrieve location information
* Provide Google Maps links

Example:

```
Find dog-friendly parks near New York
```

The agent calls the Maps MCP server and returns real-world location information.

---

## BigQuery MCP Toolset

Provides structured data analysis capabilities.

Connected Dataset:

```
nyc_dogs.licenses
```

Features:

* Query NYC dog licensing data
* Analyze dog breed statistics
* Extract insights from public datasets

Example:

```
What are the most popular dog breeds in NYC?
```

The agent creates BigQuery requests and summarizes the results.

---

# Features

* AI-powered pet travel assistant
* Google ADK based agent architecture
* Model Context Protocol integration
* Google Maps tool connectivity
* BigQuery data analytics
* Natural language interaction
* Cloud-ready architecture
* Environment based configuration

---

# Technology Stack

| Technology                         | Purpose                     |
| ---------------------------------- | --------------------------- |
| Google Agent Development Kit (ADK) | Agent framework             |
| Gemini 2.5 Flash                   | AI reasoning model          |
| Model Context Protocol (MCP)       | Tool communication protocol |
| Google Maps Platform               | Location intelligence       |
| Google BigQuery                    | Data analysis               |
| Python                             | Backend development         |
| Google Cloud Run                   | Deployment                  |
| Google Cloud Platform              | Cloud infrastructure        |

---

# Project Structure

```text
petpassport/

├── agent.py
│   └── Agent definition and instructions

├── tools.py
│   └── MCP server connections

├── .env
│   └── Environment variables

├── requirements.txt
│   └── Python dependencies

└── README.md
```

---

# Installation And Setup

## 1. Clone Repository

```bash
git clone <repository-url>

cd petpassport
```

---

## 2. Create Virtual Environment

Linux/macOS:

```bash
python3 -m venv .venv

source .venv/bin/activate
```

Windows:

```bash
python -m venv .venv

.venv\Scripts\activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Configure Environment Variables

Create a `.env` file:

```env
GOOGLE_CLOUD_PROJECT=your-project-id

GOOGLE_API_KEY=your-api-key

MAPS_API_KEY=your-maps-api-key
```

---

## 5. Run Locally

Start the ADK development server:

```bash
adk web
```

Open:

```text
http://127.0.0.1:8000
```

---

# Example Usage

## Location Queries

Input:

```text
Find pet-friendly parks nearby
```

Output:

```text
The agent searches Google Maps MCP and returns nearby pet-friendly locations.
```

---

Input:

```text
Find veterinary clinics near Manhattan
```

Output:

```text
The agent retrieves relevant clinics with location information.
```

---

## Data Queries

Input:

```text
Show the most common dog breeds in NYC
```

Output:

```text
The agent queries BigQuery and generates breed statistics.
```

---

# Security Practices

This project follows secure development practices.

Sensitive credentials are stored using environment variables.

Do not commit:

```text
.env files
API keys
Service account credentials
```

---

# Key Learnings

Concepts explored while building this project:

* Building AI agents with Google ADK
* Connecting LLMs with external tools
* Understanding MCP architecture
* Working with cloud-based AI systems
* Using Google Cloud services
* Processing real-world datasets
* Debugging agent-tool workflows

---

# Future Improvements

Planned extensions:

* Digital pet passport generation
* Pet vaccination record management
* International pet travel requirements
* Airline pet policy integration
* Personalized pet travel recommendations
* Multi-agent workflow support

