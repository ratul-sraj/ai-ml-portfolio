# AI / ML engineering portfolio

Six projects built against the AI Engineer, ML Engineer and Forward Deployed
Engineer tracks. Every repository runs offline, ships its own tests, and reports
measured numbers from a real run — no invented metrics, including where the
number is unflattering.

| # | Project | What it demonstrates | Measured headline |
|---|---|---|---|
| 1 | [manufacturing-rag-assistant](https://github.com/ratul-sraj/manufacturing-rag-assistant) | Hybrid BM25 + dense retrieval, RRF fusion, grounded answers with citations and refusals, evaluation harness | recall@5 1.00, MRR 0.917, refusal accuracy 0.90 on 40 questions |
| 2 | [supply-chain-sql-agent](https://github.com/ratul-sraj/supply-chain-sql-agent) | Text-to-SQL agent loop with guardrailed execution, self-repair, and an MCP server | 100% intent coverage offline; 0/20 on independently phrased held-out questions — reported, not hidden |
| 3 | [spam-classifier-tfidf-vs-transformer](https://github.com/ratul-sraj/spam-classifier-tfidf-vs-transformer) | TF-IDF baseline vs fine-tuned DistilBERT, deduplication, bootstrap confidence intervals | F1 0.933 vs 0.946; ΔF1 95% CI [-0.027, +0.056] — transformer not significantly better |
| 4 | [rag-eval-dashboard](https://github.com/ratul-sraj/rag-eval-dashboard) | Retrieval and agent metrics, LLM-as-judge with calibration, regression gate for CI | Judge κ 0.55 vs human labels; gate fails a seeded regression (4/8 metrics) |
| 5 | [downtime-forecast-mlops](https://github.com/ratul-sraj/downtime-forecast-mlops) | MLflow tracking, cost-sensitive thresholding, drift detection, FastAPI serving, Airflow DAG | PR-AUC 0.900 vs 0.034 base rate; $48.7k saved over a 0.5 threshold on the test split |
| 6 | [manufacturing-rag-fullstack](https://github.com/ratul-sraj/manufacturing-rag-fullstack) | React + TypeScript front end, OIDC Authorization Code + PKCE, CSRF, role gates, FastAPI backend | 44 backend tests, 10 frontend tests, production build 184 kB JS |

## How to read these

- **Each repo has a `README.md` with an evaluation table and a limitations
  section.** Start there.
- **Each repo runs without API keys.** The LLM paths are implemented and
  documented, but every test, evaluation and demo has a deterministic offline
  mode so results are reproducible by anyone.
- **CI is green on all six** (`pytest`, plus `npm build`/`test` for the
  full-stack one).

## Stack

Python 3.11 · FastAPI · scikit-learn · PyTorch / Hugging Face Transformers ·
SQLite · Streamlit · React 18 + TypeScript + Vite · Docker · GitHub Actions ·
MLflow · Airflow (DAG, importable without Airflow installed) · pypdf

## Author

Ratul S Raj — MEP/HVAC engineer moving into AI engineering.
[LinkedIn](https://linkedin.com/in/ratul-s-raj) · [LoadLens case study](https://loadlens.net/case-study.html)
