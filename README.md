# Plug & Wifi

> **UCD MSc Computer Science Research Practicum — collaborative team project.**
> This repository is a personal portfolio mirror of the [original team repository](https://github.com/Research-Practicum-Group-4/plugandwifi), not a solo-authored project. Original commit authorship and team contributions are preserved.

## Portfolio Overview

**Plug & Wifi** helps people discover and book work-friendly venues based on Wi-Fi, plug availability, quietness, location, amenities, and availability. The project combines a React web app, a React Native mobile prototype, a FastAPI backend, and data/ML workflows.

- **My role:** Backend Developer — Python/FastAPI APIs, PostgreSQL/SQLAlchemy, authentication, booking workflows, search, and integrations.
- **Team stack:** FastAPI, SQLAlchemy, Pydantic, PostgreSQL, React, TypeScript, React Native, Docker, Google Cloud, and Python ML tooling.
- **Verified contribution record:** [54 original PRs authored by `sunminlee-ucd`, 50 merged](https://github.com/sunminlee-ucd/plug-and-wifi/issues/1) (reviewed 21 October 2026).
- **Project status:** Research practicum portfolio archive. See the original README's historical demo URL below; live hosting is not guaranteed.

### Selected backend work (linked to original team PRs)

| Area | Implementation | Evidence |
| --- | --- | --- |
| Authentication & security | OAuth2/JWT authentication, rotating refresh tokens, session revocation and role-based access control | [#32](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/32), [#56](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/56), [#59](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/59) |
| Booking integrity | Concurrent seat-capacity checks with database row locking, booking cancellation and availability APIs | [#57](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/57), [#55](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/55), [#76](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/76) |
| Venue discovery | Geospatial sorting, search filters and availability-aware discovery | [#43](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/43), [#99](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/99) |
| Recommendations | Weighted suitability scoring and zone-busyness model integration in venue APIs | [#85](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/85), [#95](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/95) |
| Provider/admin & AI integrations | Provider KPI endpoint, admin overview, Gemini backend and venue-aware chatbot search | [#61](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/61), [#67](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/67), [#80](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/80), [#98](https://github.com/Research-Practicum-Group-4/plugandwifi/pull/98) |

### Contribution & project links

- [Original team repository and pull request discussions](https://github.com/Research-Practicum-Group-4/plugandwifi)
- [All 142 original PRs, with original authors and links](https://github.com/sunminlee-ucd/plug-and-wifi/issues/1)
- [Detailed backend contribution and CV reference](https://github.com/sunminlee-ucd/plug-and-wifi/issues/2)
- [Backend setup](backend/README.md) · [Web setup](frontend-web/README.md) · [Mobile setup](frontend-mobile/README.md)

---

## Original Project Documentation
Plug & Wifi is a monorepo for a flexible workspace discovery and booking
platform. The project combines a React web app, a React Native mobile prototype,
a FastAPI backend, and data/ML workflows for venue scoring and busyness-aware
recommendations.

This codebase originated as a team research-practicum project workspace. The web and
backend services are the most complete development targets; the mobile and
data/ML directories support prototype, experimentation, and integration work.

## Production URL

Historical production URL: https://plugandwifi.xyz/

The original deployment URL was stated to be valid only until **25 August 2026**;
it should not be assumed to be a currently available live demo.

## Current Scope

- discover venues suitable for remote work and study
- view venue details, opening information, amenities, ratings, prices, and map location
- sign up, log in, save favorite venues, and view booking history
- create bookings and complete a mock payment flow
- support provider registration, venue submission, dashboard, arrivals, and booking completion
- support admin review, pending applications, taxonomy, and venue moderation workflows
- use venue CSV data and ML artifacts for busyness diagnostics and suitability scoring
- provide mock frontend data paths for UI development without a running backend

## Repository Layout

```text
plugandwifi/
|-- backend/
|   |-- app/
|   |-- test/
|   |-- Dockerfile
|   `-- README.md
|-- frontend-web/
|   |-- src/
|   |-- public/
|   |-- Dockerfile
|   `-- README.md
|-- frontend-mobile/
|   |-- src/
|   |-- android/
|   |-- ios/
|   `-- README.md
|-- data-ml/
|   |-- src/
|   |-- models/
|   |-- notebooks/
|   `-- requirements.txt
|-- data/
|-- docs/
|-- CONTRIBUTING.md
`-- README.md
```

## Stack

| Area | Current choice |
| :--- | :--- |
| Web frontend | React 18, TypeScript, Vite, Tailwind CSS 4, React Router 7 |
| Mobile frontend | React Native 0.85, React 19, React Navigation |
| Backend | FastAPI, SQLAlchemy, Pydantic |
| Database | PostgreSQL for local development, SQLite in backend tests |
| Data / ML | Python, pandas, scikit-learn, xgboost, joblib |
| Testing | Vitest, Testing Library, Jest, pytest |
| Containers | Dockerfiles for backend and web frontend |

## Project Planning Documents

The main planning artefacts are stored under `docs/`:

| Document | Path |
| :--- | :--- |
| Product backlog | `docs\Plug&Wifi — Product Backlog.md` |
| Sprint backlog | `docs\Plug & Wifi – Final Sprint Backlog.csv` |
| Sprint Timeline | `docs\Plug_and_Wifi_Story_Timeline.png` |
| Interview documentation | `docs\P&W_interviews.pdf` |
| Project budget table | `docs\Plug_and_Wifi_Jira_Actual_Hours_Budget.xlsx` |
| Sprint burndown chart | `docs\sprint_burndown_chart.pdf` |

Use these files as the source for feature scope, sprint commitments, and
planning traceability.

## Design Mockups

| Mockup | Link |
| :--- | :--- |
| Web mockup | https://feast-prove-58453607.figma.site/ |
| Mobile mockup | https://drive.google.com/drive/folders/1c0srv0GCkpuj1dDKU6rwPnKIvlWnH4fk?usp=sharing |

## Service Documentation

Each major service has its own setup instructions:

| Area | README |
| :--- | :--- |
| Backend API | `backend\README.md` |
| Web frontend | `frontend-web\README.md` |
| Mobile frontend | `frontend-mobile\README.md` |

The backend README covers PostgreSQL setup, venue CSV import from
`data-ml\models\nyc_venues.csv`, one-off migration scripts, busyness model
artifacts, and Docker usage.

The web README covers mock mode, real backend mode, environment variables,
Google Maps configuration, tests, Docker usage, and route overview.

## Quick Start

The usual local development path is to run the backend and web frontend
together.

1. Set up the backend.

```bash
python -m venv .venv
python -m pip install -r backend/requirements.txt
```

Then follow `backend\README.md` for:

- creating the PostgreSQL database
- creating `backend\.env`
- downloading the Google Drive ML artifacts
- placing `nyc_venues.csv` in `data-ml\models\nyc_venues.csv`
- creating the schema
- running `backend.app.seed_venues`
- starting FastAPI on port `8080`

2. Start the backend from the repository root.

```bash
python -m uvicorn backend.app.main:app --reload --port 8080
```

Backend docs are available at:

```text
http://localhost:8080/docs
```

3. Set up and start the web frontend.

```bash
cd frontend-web
npm install
npm run dev:local
```

Open:

```text
http://localhost:5173
```

For frontend-only work, use mock mode instead:

```bash
cd frontend-web
npm install
npm run dev
```

## Docker Overview

The backend image must be built from the repository root because it copies both
`backend/` and `data-ml/src/`:

```bash
docker build -f backend/Dockerfile -t plugandwifi-backend .
```

The web frontend image should be built from `frontend-web/` because its
Dockerfile expects the frontend package files as the build context:

```bash
cd frontend-web
docker build -t plugandwifi-frontend .
```

See the service READMEs for complete Docker run commands, environment
variables, mounted model files, and local database notes.

## Tests

Backend tests:

```bash
python -m pytest backend/test
```

Web frontend tests:

```bash
cd frontend-web
npm run test
```

Mobile tests:

```bash
cd frontend-mobile
npm test
```

## Development Notes

- Follow `CONTRIBUTING.md` for branch, PR, and review workflow.
- Treat service-specific READMEs as the source of truth for setup details.
- Keep local secrets and API keys in ignored `.env*` files.
- The backend and web frontend are the main end-to-end demo path.
- The data/ML workflow provides the venue CSV and busyness artifacts consumed by the backend.
