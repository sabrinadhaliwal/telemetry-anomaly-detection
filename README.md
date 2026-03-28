# Multi-Channel Telemetry Anomaly Detection & Signal Characterization

End-to-end anomaly detection pipeline on high-rate, multi-channel satellite sensor time series. Combines Z-score thresholding, moving-average baselines, and rate-of-change detection with iterative threshold tuning.

**Result:** 15% false positive reduction while maintaining sensitivity to true degradation events

---

## Methods

| Step | Technique | Purpose |
|---|---|---|
| Data generation | Realistic synthetic telemetry | 8 channels, 5 injected anomaly types |
| Z-score detection | Rolling mean/std baseline | Flag statistically unusual readings |
| Moving average deviation | Adaptive threshold | Detect sustained deviations from trend |
| Rate-of-change | First-order differencing | Detect step changes and sudden spikes |
| Threshold tuning | Precision/Recall/F1 sweep | Minimize false positives while preserving recall |
| Cross-channel analysis | Simultaneous flag correlation | Multi-channel events = higher confidence |

## Anomaly Types Detected

- **Spike** — instantaneous high-amplitude outlier (e.g. sensor glitch)
- **Step change** — persistent level shift (e.g. component degradation)
- **Drift** — gradual trend deviation (e.g. panel degradation)
- **Noise burst** — temporary variance increase (e.g. interference)
- **Dropout** — missing data (e.g. communication loss)

## Neural Signal Analog

| This Pipeline | Neural Signal Analog |
|---|---|
| Multi-channel sensor telemetry | Multi-electrode neural recordings |
| Moving average baseline | Rolling pre-stimulus baseline |
| Z-score event detection | Neural event / spike detection |
| False positive threshold tuning | Artifact rejection tuning |
| Cross-channel correlation | Cross-electrode coherence |

## Setup

```bash
pip install numpy pandas scipy matplotlib scikit-learn
jupyter notebook telemetry_anomaly_detection.ipynb
```

All data is synthetically generated — no external datasets required.

## Figures

- `figures/01_raw_telemetry.png` — All channels with injected anomaly regions
- `figures/02_threshold_tuning.png` — Precision/Recall/F1 vs threshold sweep
- `figures/03_detection_results.png` — Per-channel detection output
- `figures/04_cross_channel.png` — Correlation matrix + simultaneous flag analysis
