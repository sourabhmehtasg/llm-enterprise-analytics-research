# Schema Maturity Scorer
### LLM Analytics Readiness for Enterprise Data

**Sourabh Mehta** | Research in Progress, March,2026 | MVP v1.0

---

A lightweight tool that evaluates a relational star schema for readiness before
deploying LLM-based natural language analytics. Paste a DDL file, get a
readiness score with actionable remediation guidance.

**[→ Open the Tool](https://schema-maturity-scorer.netlify.app/)**

---

## Why This Exists

Enterprise databases are not built for LLMs. Column names are cryptic, business
logic is buried in status codes, foreign key relationships are implied but not
declared, and numeric values are often stored as text. LLM-based analytics
deployed on such schemas produce plausible-looking but incorrect results —
often silently, with no error message.

This tool helps teams identify schema-side risk before deployment.

---

## What It Scores

A single star schema (one data mart) is evaluated across four dimensions.

| Dimension | Weight |
|---|---|
| Column Naming Clarity | 30% |
| Relationship Documentation | 25% |
| Data Type Correctness | 25% |
| Column Ambiguity | 20% |

**Score Bands**

| Score | Label |
|---|---|
| 80 – 100 | LLM Ready |
| 60 – 79 | Enrichment Required |
| 40 – 59 | High Risk |
| 0 – 39 | Not Recommended |

---

## Scope

- Evaluates one data mart at a time — intentional by design
- DDL input only — no database connection required
- No installation — runs entirely in the browser
- Code value transparency requires data upload and is planned for a future version

---

## Roadmap

- [ ] Data upload for Code Value Transparency scoring
- [ ] Schema comparison — before and after remediation
- [ ] Export remediation report as PDF
- [ ] Multi-dialect support — Oracle, SQL Server, PostgreSQL
- [ ] API endpoint for CI/CD pipeline integration

---

## Research Context

This tool is a practical output of ongoing research into LLM reliability for
enterprise analytics. The scoring dimensions are informed by documented failure
patterns in published Text-to-SQL research.

Key references:

- Yu et al. (2018) — Spider: benchmark schemas are clean by design; enterprise
  messiness is explicitly excluded
- Gao et al. (2023) — DAIL-SQL: near-perfect benchmark scores collapse on
  realistic schema variants
- Chen et al. (2025) — LinkedIn production deployment: 53% correctness after
  18 engineers and full knowledge graph infrastructure
- Kryscinski et al. (2019) — FactCC: AI systems produce plausible but factually
  incorrect outputs at scale, invisible to standard accuracy metrics

The tool operationalises schema-side risk factors identified across this body of
work. The underlying research is in progress.

---

## Preprint

A research abstract is available on ResearchGate:
**[→ View Research Abstract](RESEARCHGATE-URL)**

---

*For enquiries contact via GitHub profile.*
