# THz-TD Loss Landscapes

This repository contains tools for visualizing and analyzing loss landscapes in Terahertz Time-Domain Spectroscopy (THz-TDS) systems.  
It supports the simulation of reference and sample pulses using the matrix transfer method, and provides several Jupyter notebooks to explore how different sample parameters affect model loss.  
NOTE: The loss generation has not been optimized, it is linear and single threaded.

---

## 📁 Project Structure

```
THz-TD-Loss_landscapes-main/
│
├── 3_d_loss_landscape.ipynb              # 3D loss landscape exploration (n, k, d)
├── Loss_landscape-2d.ipynb               # 2D loss landscape visualization
├── Single_layer_loss.ipynb               # Single-layer loss computation
├── single_layer_loss_all_params.ipynb    # Sweeps across n, k, d for a single layer
├── thickness_and_n_loss.ipynb            # Loss landscapes for thickness vs refractive index
│
├── Matrix_methods/                       # Core simulation and optimization code
│   ├── AdamExtractor.py                  # Gradient-based optimizer wrapper
│   ├── BayesianExtractor.py              # Bayesian optimization utilities
│   ├── Simulate.py                       # Matrix method for THz propagation simulation
│   ├── oldSimulate.py                    # Older simulation version (for reference)
│   └── __init__.py
│
├── data/
│   └── example_ref_pulse.csv             # Example reference pulse data (CSV)
│
├── loss plots/                           # Precomputed loss landscape plots
│   ├── Loss_at_true_d_zoomed.png
│   ├── all_params_free.png
│   ├── all_params_free_4_panes.png
│   ├── anomalous_area.png
│   └── ...
│
└── .gitignore                            # Git ignore file for Python and data artifacts
```

---

## 🚀 Getting Started

### Prerequisites

You'll need Python 3.8+ with the following libraries:

- `numpy`
- `matplotlib`
- `plotly` *(for interactive 3d plots)*
- `scipy`
- `pandas`
- `scikit-learn`
- `torch`
- `skopt` *(for Bayesian optimization)*

Install all dependencies using:


---

## 📊 Usage

Each notebook explores different views of the loss landscape by varying combinations of sample parameters:

- **Refractive index (n)**
- **Extinction coefficient (k)**
- **Layer thickness (d)**

To run:

1. Open a notebook (e.g. `Single_layer_loss.ipynb`) in Jupyter Lab or VSCode.
2. Run all cells.
3. Explore the resulting plots.

---

## 🧠 Methodology

THz-TDS systems are modeled using a matrix transfer method, where the simulated pulse is propagated through a multilayer stack. The predicted time-domain signal is compared to a measured reference, and loss is computed as the mean squared error (MSE).

This loss surface is then visualized to explore:
- Identifiability of parameters
- Gradient quality for optimization
- Degenerate or ill-posed regions

Optimization strategies like **Adam** and **Bayesian Optimization** are included to find parameters minimizing the loss.

---

## 📷 Example Visualizations

![Loss at True d Zoomed](loss%20plots/Loss_at_true_d_zoomed.png)


---

## 🤝 Contributing

Contributions are welcome! If you'd like to add new optimization strategies or visualization modes, feel free to submit a pull request.

---

