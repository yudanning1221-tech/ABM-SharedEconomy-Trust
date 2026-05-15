# ABM-SharedEconomy-Trust

> Agent-based simulation of trust dynamics and youth labor relations in sharing economy platforms

## Overview

This project builds an Agent-Based Model (ABM) to simulate how platform governance strategies drive the evolution of trust among gig economy workers. The model is implemented in **NetLogo 7.0.3** and includes 175 workers (80% youth), 77 consumers, and a single platform agent. A total of **390 Monte Carlo simulations** were conducted across four experimental groups.

This is the replication repository for the paper:

> **"Trust Mechanism and Youth Labor Relations in Sharing Economy: An ABM Simulation Study"**

---

## Repository Structure

```
ABM-SharedEconomy-Trust/
├── models/
│   ├── main_model.nlogo          # Core ABM model
│   └── main_model_exp.nlogo      # Experimental variant
│
├── experiments/
│   ├── exp1_incentive_intensity/ # Experiment 1: Incentive intensity scan
│   ├── exp2_external_shock/      # Experiment 2: External shocks
│   ├── exp3_reputation_mechanism/# Experiment 3: Reputation mechanism switch
│   └── exp4_youth_ratio/         # Experiment 4: Youth ratio gradient
│
├── docs/
│   ├── model_user_guide_v2.4.docx
│   ├── experiment_full_report.docx
│   ├── model_calibration.docx
│   └── appendix.docx
│
├── paper/
│   ├── paper_main.docx           # Final paper
│   └── paper_draft.docx
│
├── .gitignore
└── README.md
```

---

## Model Design

### Agents

| Agent | Count | Description |
|-------|-------|-------------|
| Workers | 175 | 80% youth (age 16–35), 20% non-youth |
| Consumers | 77 | 50% trust-type, 50% threshold-type |
| Platform | 1 | Sets and enforces governance rules |

### Core Parameters

| Parameter | Symbol | Default Value |
|-----------|--------|---------------|
| Incentive coefficient | αe | 0.7 |
| Control coefficient | αc | 0.4 |
| Transparency | τ | 0.7 |
| Imitation rationality | β | 0.5 |
| Reputation elimination threshold | Rc | 0.08 |

### Key Mechanisms

- **Fermi Imitation Dynamics** — workers update strategies by imitating higher-earning peers
- **Asymmetric Reputation Update** — penalties for distrust outweigh rewards for trust (κ×λ = 1.56)
- **Adaptive Governance** — platform adjusts αe/αc every 10 steps based on average trust level
- **Youth Reactance** — youth workers are 40% more likely to trigger reactance when αc > 0.7

---

## Experiments

| # | Experiment | Key Finding |
|---|-----------|-------------|
| Exp 1 | Incentive intensity scan | Dual non-monotonic effect: high incentive raises overall trust but lowers trustworthy worker ratio by ~22% |
| Exp 2 | External shocks (order drop / algorithm mutation) | System shows strong self-recovery resilience under high-incentive steady state |
| Exp 3 | Reputation mechanism on/off | No significant effect on overall trust (p=0.492), but significantly raises trustworthy ratio (p<0.001) |
| Exp 4 | Youth ratio gradient | Youth ratio has no significant main effect on trust steady state under moderate control (αc < 0.7) |

---

## How to Run

1. Install [NetLogo 7.0.3](https://ccl.northwestern.edu/netlogo/)
2. Open `models/main_model.nlogo`
3. Click **Setup** then **Go**
4. For batch experiments, use **BehaviorSpace** (Tools → BehaviorSpace)

---

## Requirements

- NetLogo 7.0.3
- Python 3.x + pandas / numpy (for data analysis scripts)

---

## Authors

- **Danning Yu** — Platform mechanism design, simulation, empirical analysis
- Shanghai International Studies University, School of International Finance and Trade

---

## License

This repository is private. All rights reserved. Not for redistribution without permission.
