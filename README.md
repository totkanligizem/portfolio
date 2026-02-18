# Data Science & AI Portfolio

This repository is the central hub for my applied work in **Data Science, Machine Learning, Deep Learning, and Artificial Intelligence**.

Projects focus on solving real-world problems with an emphasis on:
- end-to-end ML pipelines,
- analytical rigor,
- interpretability,
- and measurable business impact.

---

## What you'll find here
- **End-to-end Machine Learning projects** (EDA → feature engineering → modeling → evaluation → deployment-ready structure)  
- **Analytics & KPI-driven dashboards** (business-oriented insights and decision support)  
- **NLP & LLM-based applications** (RAG, embeddings, semantic search)  
- **Case studies and technical deep-dives** (methodology, assumptions, trade-offs, and results)

---

## Featured Projects

### 1) [Basket AI — Market Basket Recommender](https://github.com/totkanligizem/basket_ai)
End-to-end recommendation pipeline: data prep → candidate generation → ranking → evaluation.  
**Highlights:** association rules + co-occurrence signals • offline metrics (Recall@K / NDCG@K) • reproducible notebooks & scripts  
**Stack:** Python • pandas • scikit-learn

---

### 2) [AI Hub — E-Commerce: Predictive Ops + Grounded RAG + Sentinel Cockpit](https://github.com/totkanligizem/ai-hub-cloud)
End-to-end e-commerce analytics and decision-support platform that combines **predictive operations**, **grounded LLM assistance**, and an **action-oriented risk diagnosis layer** in a single cockpit UI.

#### What it does
- **Predictive Ops (BigQuery ML)**
  - **Churn modeling (TheLook)** using a training view (`vw_churn_training`) and a deployed model (`churn_model`)
  - **Delivery delay modeling (Olist)** with two modeling approaches:
    - `delay_prediction_model` (linear)
    - `delay_prediction_bt_model` (boosted tree)
  - Outputs include prediction tables, calibration artifacts, and **precision@k**-oriented evaluation tables.

- **Simulation QA**
  - Simulates delivery delays for TheLook orders using Olist delay distributions
  - Includes drift validation with **PSI / KS** checks via `delay_simulation_validation`

- **Grounded RAG + Chat (BigQuery + Vertex AI)**
  - Builds an e-commerce product corpus: `rag_product_corpus` (Olist + TheLook)
  - Generates embeddings into `product_embeddings`
  - Supports two chatbot profiles:
    - **Concierge**: product/fashion focus with **ID-free queries**
    - **Operations**: risk/order focus with optional `order_id` / `user_id` context

- **Sentinel Action Assistant**
  - Interprets risk signals, produces **confidence-aware** diagnostics, and returns an actionable plan
  - Supports order support workflows and geo-focused handoff in the UI

- **Streamlit Cockpit**
  - A single interface for operations insights, quality checks, and concierge-style grounded Q&A

#### Architecture
- Raw datasets (read-only): `olist_ecommerce`, `thelook_ecommerce`
- Serving dataset: `ai_hub_core`
- LLM: `gemini-2.5-flash`
- Embedding model: `text-embedding-004`

#### Repo layout
- SQL / model building: `sql/ddl/`, `sql/models/`, `sql/analysis/`
- Backend: `src/backend/bq_client.py`, `src/backend/vector_search.py`, `src/backend/ops_chatbot.py`, `src/backend/sentinel_agent.py`
- Frontend: `src/frontend/app.py`
- Scripts: `scripts/run_phase2_all.sh`, `scripts/run_phase2_sql.sh`, `scripts/security_preflight_check.py`
- Tests: `tests/unit/`, `tests/manual_*.py`

#### Security-first practices
- Service account JSON kept **outside** the repo
- `.env`-based configuration with `.env.example`
- Preflight checks + push-safe secret scanning checklist to prevent accidental credential leakage

#### Stack
Python • BigQuery ML • Vertex AI (Gemini) • Vector Search / Hybrid Retrieval • Streamlit

---

## Current status
Projects are being added progressively.

Each project is published once it includes:
- a clear problem definition,
- reproducible code,
- documented assumptions,
- and interpretable results.

---

## Contact
- LinkedIn: <https://linkedin.com/in/totkanligizem>  
- Kaggle: <https://kaggle.com/gtotkanli>
