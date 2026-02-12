# Droplet Dynamics Predictor
---
### Week 1: Updates 
Have successfully created a boilerplate model for determining the position of the droplets. 

##  System Overview

This project implements a **Hybrid Lagrangian** machine learning framework to predict droplet dynamics (velocity fields and trajectories) in computational fluid dynamics (CFD) simulations.

The architecture will be designed for a **local-cloud hybrid workflow**:
* **Local Environment:** Visual Studio Code (Debian) for code editing and version control. 
* **Remote Compute:** Google Colab (Linux VM + GPU) for high-performance execution.
* **Data Bridge:** Google Drive for persistent storage of input data (`.dat`) and output models (`.txt`).
  Currently this model is trained and created on Google Colab. As the volume of training data will increase, we will shift to more powerful workstations. 

### Core Methodology
The model predicts the velocity vector $\vec{v}_t$ for a droplet based on its state at $t-1$:
$$\vec{v}_t = f(t, V, A, \vec{x}_{t-1})$$
Where $V$ is Volume, $A$ is Surface Area, and $\vec{x}$ is the coordinate vector.

---

## Resources used 

 https://www.sciencedirect.com/science/article/pii/S0263224123008345
---


##  Prerequisites

### Software
* **Local Machine:**
    * Visual Studio Code
    * Extension: **Google Colab** 
* **Cloud:**
    * Google Account with access to Drive and Colab.

### Data Format
The system requires a whitespace-separated ASCII file (`.dat`) with **no header row**.
The columns must strictly follow this schema:

| Index | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| 0 | `step` | int | Computational time step |
| 1 | `time` | float | Physical simulation time |
| 2 | `id` | int | Unique droplet identifier |
| 3 | `volume` | float | Droplet volume |
| 4 | `x` | float | X coordinate |
| 5 | `y` | float | Y coordinate |
| 6 | `z` | float | Z coordinate |
| 7 | `area` | float | Surface area |

---

## 3. Installation & Setup
Use this link to view the notebook in Colab.
https://colab.research.google.com/drive/1e7eBbjyJmk90ApWEjzFBWtJuxk4kM73O?authuser=2#scrollTo=M0PV0k7mgPvY

Please keep in mind that this is a boilerplate code, just to understand the training data and test the capabilites of my Laptop.
I will also keep updating the Readme 
