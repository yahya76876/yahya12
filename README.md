# DAG structure
raw_task >> transform_task >> load_task
```
**Ce projet :** ✅ Pipelines séparés = futur DAG facile à créer

---

### **4. Architecture dbt (Data Build Tool)**
```
sources (raw) → staging (cleaning) → marts (business logic)
```
**Ce projet :** ✅ Même philosophie de transformation progressive

---

## 🚀 Points forts de cette architecture

| ✅ Avantage | Impact |
|-------------|---------|
| **Séparation des responsabilités** | Code maintenable |
| **Scalabilité** | Facile d'ajouter de nouveaux pipelines |
| **Testabilité** | Dossier `tests/` dédié |
| **Reproductibilité** | Config externalisée |
| **Collaboration** | Templates GitHub PR |
| **Évolutivité** | Prêt pour Airflow/Prefect |

---

## 🔄 Évolutions possibles (standards industrie)

### Version avancée de cette architecture :
```
part-1/
├── data/
│   ├── raw/          # Bronze
│   ├── staging/      # Silver (ajout)
│   └── curated/      # Gold
│
├── src/
│   ├── pipelines/
│   │   ├── ingestion/     # Extract
│   │   ├── transformation/ # Transform
│   │   └── serving/       # Load
│   ├── models/            # Data models (pydantic)
│   ├── validators/        # Data quality checks
│   └── orchestration/     # Airflow DAGs
│
├── infrastructure/        # Terraform/Docker
├── notebooks/            # Jupyter pour exploration
├── docs/                 # Documentation Sphinx
│
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── setup.py
└── pyproject.toml
