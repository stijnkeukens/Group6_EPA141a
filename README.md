# Group6_EPA141a

# EPA141A — Assignments 4–8
**Actor 15 — Japan & South Korea | Delft University of Technology**

---

## Important

This repository does **not** include the JUSTICE model or the course environment — these are too large to upload and you should already have them from Canvas. This repo only contains:

- The five notebooks (`assignment_04` – `assignment_08`)
- The config file (`config/config_student.json`)
- The results folder (`results/`) with all pre-computed output files

**Just download this repo and drop the files into your existing `epa141a-main/` folder. Everything will work from there.**

---

## How to install

1. Download or clone this repository
2. Copy the contents into your existing `epa141a-main/` course folder:
   - The five `.ipynb` notebooks → root of `epa141a-main/`
   - `config/config_student.json` → into `epa141a-main/config/`
   - Everything in `results/` → into `epa141a-main/results/`
3. Activate the course environment and open JupyterLab:

```bash
conda activate epa141a
jupyter lab
```

4. Run the notebooks top-to-bottom in order (A4 → A5 → A6 → A7 → A8).

> The `results/` folder already contains all pre-computed files (reference set, convergence archive, re-evaluation cache), so you can open A6, A7 and A8 directly without re-running the optimisation.

---

## Assignment Summaries

**A4 — Problem Formulation**
Defines the XLRM framework: 4 uncertainties, 244 RBF levers, 4 objectives (all lower-is-better). Saves `config/config_student.json` with the chosen welfare function (Utilitarian), reference scenario (SSP2-RCP4.5), and epsilon values.

**A5 — Many-Objective Optimisation**
Runs GenerationalBorg (50 000 NFE, 1 seed) and produces `results/reference_set_utilitarian.csv` — 10 non-dominated policies. All downstream notebooks read this file.

**A6 — Convergence Analysis**
Computes hypervolume, epsilon-progress, generational distance and epsilon-indicator. Finding: epsilon-progress had not fully plateaued at 50 000 NFE; the front is an underestimate of the true Pareto front.

**A7 — Pareto Visualisation**
Parallel-coordinates plot of the reference set and world ECR maps for four anchor policies (W, R, D, Ab). Key finding: welfare barely varies; the real trade-off is climate risk vs. abatement cost.

**A8 — Robustness Analysis**
Re-evaluates 10 policies across 50 FaIR scenarios. Applies satisficing (mandate-tuned thresholds) and minimax regret. Recommended policy: **P2** — highest satisficing score and lowest regret coincide.
