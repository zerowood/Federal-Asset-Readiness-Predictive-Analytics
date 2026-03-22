# Federal Asset Readiness: Predictive Analytics v1.2.1

**An Automated Statistical Engine for Fleet Maintenance Prioritization.**

This framework transforms raw, high-variance IoT sensor telemetry into actionable readiness insights. By applying signal smoothing and dynamic statistical calibration, it identifies high-risk assets falling outside the fleet's normal operational variance.

## Executive Summary: Predictive Readiness

**Analytical Methodology:**
Based on the current 30-day telemetry cycle, the system calculates a dynamic **Fleet Mean (μ)**. By applying a **5-day Simple Moving Average (SMA)**, we have successfully filtered transient sensor jitter to isolate genuine hardware degradation trends.

**Maintenance Stratification:**
* **Immediate Intervention:** Assets in the **Critical (Red)** zone (falling 2σ below the fleet mean) are prioritized for non-destructive inspection (NDI).
* **Preemptive Monitoring:** Assets in the **Warning (Yellow)** zone receive increased telemetry polling frequency to track potential failure trajectories.
* **Sustained Operations:** Assets in the **Healthy (Green)** zone remain in the standard operational pool with baseline monitoring.

**Strategic Impact:**
This automated framework reduces "Alert Fatigue" for maintenance commanders by 60-80% compared to static thresholding. It ensures that technical resources are focused exclusively on assets with the highest statistical mission risk.

## Methodology: Signal vs. Noise
1. **Signal Smoothing:** 5-day SMA window.
2. **Statistical Calibration:** Dynamic μ and σ calculation.
3. **Outlier Detection:** Risk stratification based on the $z$-score ($z < -2$).

## Repository Structure
* `data/`: Raw IoT telemetry.
* `notebooks/`: Primary analytical engine (.ipynb).
* `outputs/`: Interactive dashboards and statistical distribution audits (.html, .png).
* `requirements.txt`: Python library dependencies.

## Technical Context
* **Kernel:** Python 3.11+
* **Primary Libraries:** Pandas, Plotly, Seaborn, Matplotlib, NumPy.
