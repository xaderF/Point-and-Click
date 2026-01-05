# Point-and-Click (CSCS207 Final Project)

A **point-and-click puzzle/adventure game** built as a **CSCS207 class final project**. The game integrates a **Riddle API** to fetch questions dynamically and uses a **Clean Architecture** structure to keep business logic independent from UI and external services. :contentReference[oaicite:0]{index=0}

> **School Project Note**
> This repository was created for an academic course project. It is intended for learning and demonstration purposes (architecture, testing, and collaboration), not production deployment. :contentReference[oaicite:1]{index=1}

---

## Table of Contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Clone & Build](#clone--build)
  - [Run](#run)
- [How the Riddle API is Used](#how-the-riddle-api-is-used)
- [Clean Architecture](#clean-architecture)
  - [Layer Responsibilities](#layer-responsibilities)
  - [Dependency Rule](#dependency-rule)
  - [Typical Request Flow](#typical-request-flow)
- [Project Structure](#project-structure)
- [Testing](#testing)
- [Configuration](#configuration)
- [Academic Integrity](#academic-integrity)
- [Credits / Acknowledgements](#credits--acknowledgements)

---

## Project Overview
**Point-and-Click** is a small adventure-style game where the player interacts with the scene through clicking/selection, and progresses by solving riddles pulled from an external API. The goal is to demonstrate:
- separation of concerns with Clean Architecture,
- testable business rules,
- external API integration behind interfaces/adapters,
- a maintainable codebase suitable for a team course project. :contentReference[oaicite:2]{index=2}

---

## Key Features
- **Point-and-click interaction loop** (navigate / inspect / interact)
- **Riddle-driven progression** using an external Riddle API (fetch question + validate answer)
- **Clean Architecture layout** (entities/use cases decoupled from UI & network)
- **Extensible design**: swap API providers or UI framework without rewriting core logic
- **Unit-test-friendly**: core use cases can be tested with fake gateways/services

---

## Tech Stack
This repository is primarily **Java**. :contentReference[oaicite:3]{index=3}

**Build**
- **Maven** (`pom.xml`) for dependency management and build automation

**Core Concepts / Patterns**
- Clean Architecture (Entities → Use Cases → Interface Adapters → Frameworks/Drivers)
- Dependency Inversion (interfaces in inner layers, implementations in outer layers)
- Controller/Presenter separation (use cases don’t talk to UI directly)

**API / Networking**
- A dedicated API gateway/service responsible for calling the Riddle API and parsing results  
  *(See `pom.xml` for the exact HTTP + JSON libraries used.)*

**Testing**
- Unit tests for use cases (typically run via Maven test lifecycle)

> If you want this README to list **every exact dependency + version**, copy/paste your `pom.xml` here (or allow access to its raw view) and I’ll fill in an exact dependency table.

---

## Getting Started

### Prerequisites
- **Java (JDK)** installed (course projects commonly use JDK 17+; use whatever your class specifies)
- **Maven** installed (or use your IDE’s Maven integration)

### Clone & Build
```bash
git clone https://github.com/xaderF/Point-and-Click.git
cd Point-and-Click
mvn clean package
