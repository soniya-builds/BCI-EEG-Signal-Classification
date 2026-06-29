# BCI-EEG-Signal-Classification

## Overview

This project presents a complete Brain-Computer Interface (BCI) pipeline for Electroencephalography (EEG) signal preprocessing and preparation for deep learning-based classification. The workflow transforms raw EEG recordings into standardized datasets suitable for ChronoNet-based neural network training.

The project utilizes scientific Python libraries including **MNE**, **Scikit-learn**, **PyTorch**, and **PyTorch Lightning** to build a reproducible EEG preprocessing workflow.

---

## Project Information

| Attribute               | Description                    |
| ----------------------- | ------------------------------ |
| Project                 | BCI EEG Signal Classification  |
| Domain                  | Brain-Computer Interface (BCI) |
| Data Type               | Multichannel EEG Signals       |
| Programming Language    | Python                         |
| Deep Learning Framework | PyTorch                        |
| Training Framework      | PyTorch Lightning              |
| EEG Processing Library  | MNE                            |
| Machine Learning        | Scikit-learn                   |

---

## Project Objectives

* Load multichannel EEG recordings from MATLAB files.
* Preprocess EEG signals using standard neuroscience techniques.
* Convert continuous EEG recordings into fixed-length epochs.
* Prepare datasets for deep learning.
* Implement subject-wise train-validation splitting.
* Build an efficient preprocessing pipeline compatible with ChronoNet.
* Generate scientific visualizations for EEG analysis.

---

## Dataset Structure

| Dataset       | Description                                                   |
| ------------- | ------------------------------------------------------------- |
| CleanData_IDD | EEG recordings from IDD participants                          |
| CleanData_TDC | EEG recordings from Typically Developing Control participants |
| Music         | EEG recordings collected during music stimulation             |
| Rest          | EEG recordings collected during resting state                 |

Each EEG recording contains:

| Property           | Value       |
| ------------------ | ----------- |
| Channels           | 14          |
| Sampling Frequency | 128 Hz      |
| Recording Duration | 120 Seconds |
| Signal Shape       | (14, 15360) |

---

## Project Workflow

```text
Raw EEG (.mat)
        │
        ▼
Load MATLAB Files
        │
        ▼
Create MNE Raw Objects
        │
        ▼
Average Referencing
        │
        ▼
Band-pass Filtering
        │
        ▼
Epoch Generation
        │
        ▼
Dataset Construction
        │
        ▼
Label Encoding
        │
        ▼
GroupKFold Split
        │
        ▼
Feature Standardization
        │
        ▼
Tensor Conversion
        │
        ▼
ChronoNet Training
```

---

## EEG Preprocessing Pipeline

| Step                  | Description                                  |
| --------------------- | -------------------------------------------- |
| Data Loading          | Read EEG recordings from MATLAB (.mat) files |
| Raw Object Creation   | Convert recordings into MNE RawArray objects |
| Channel Configuration | Assign standard EEG channel names            |
| Referencing           | Apply average reference                      |
| Filtering             | Band-pass filtering                          |
| Epoch Extraction      | Segment recordings into fixed-length epochs  |
| Dataset Preparation   | Organize IDD and TDC samples                 |
| Label Creation        | Generate binary labels                       |
| Group Assignment      | Create subject identifiers for GroupKFold    |
| Standardization       | Normalize EEG features                       |
| Tensor Preparation    | Convert data into PyTorch tensors            |

---

## Data Preparation

The preprocessing stage generates three arrays for model training.

| File        | Description                        |
| ----------- | ---------------------------------- |
| data_array  | EEG feature array                  |
| label_array | Binary class labels                |
| group_array | Subject identifiers for GroupKFold |

---

## Technologies Used

| Category            | Libraries           |
| ------------------- | ------------------- |
| Numerical Computing | NumPy, SciPy        |
| Data Analysis       | Pandas              |
| Visualization       | Matplotlib, Seaborn |
| EEG Processing      | MNE                 |
| Machine Learning    | Scikit-learn        |
| Deep Learning       | PyTorch             |
| Training Framework  | PyTorch Lightning   |
| Utilities           | tqdm                |

---

## Visual Analysis

The notebook includes multiple visualization techniques for EEG exploration.

| Visualization              | Purpose                                  |
| -------------------------- | ---------------------------------------- |
| Raw EEG Signal             | Inspect brain signal recordings          |
| Multi-channel EEG Plot     | Observe channel-wise activity            |
| EEG Heatmap                | Visualize temporal channel activity      |
| Power Spectral Density     | Analyze frequency-domain characteristics |
| Spectrogram                | Time-frequency representation            |
| Channel Correlation Matrix | Investigate spatial relationships        |
| Dataset Distribution       | Verify class balance                     |

---

## Project Structure

```text
BCI-EEG-Signal-Classification/
│
├── notebooks/
│   ├── Data_Preparation.ipynb
│   └── ChronoNet_Training.ipynb
│
├── data/
│   ├── CleanData_IDD/
│   └── CleanData_TDC/
│
├── processed_data/
│
├── figures/
│
├── models/
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Installation

Clone the repository.

```bash
git clone https://github.com/soniya-builds/BCI-EEG-Signal-Classification.git
```

Create a virtual environment.

```bash
python -m venv env
```

Activate the environment.

### Windows

```bash
env\Scripts\activate
```

### Linux / macOS

```bash
source env/bin/activate
```

Install project dependencies.

```bash
pip install -r requirements.txt
```

---

## Current Progress

| Module                  | Status      |
| ----------------------- | ----------- |
| Dataset Loading         | Completed   |
| EEG Preprocessing       | Completed   |
| Signal Filtering        | Completed   |
| Epoch Extraction        | Completed   |
| EEG Visualization       | Completed   |
| Dataset Preparation     | Completed   |
| GroupKFold Split        | Completed   |
| Feature Standardization | Completed   |
| Tensor Preparation      | Completed   |
| ChronoNet Model         | In Progress |
| Model Training          | In Progress |
| Performance Evaluation  | Pending     |

---

## Future Work

* Complete ChronoNet model implementation.
* Evaluate classification performance.
* Generate confusion matrix and performance metrics.
* Perform hyperparameter optimization.
* Compare ChronoNet with other deep learning architectures.
* Investigate explainable AI techniques for EEG classification.

---

## Author

| Name         | Contact                                                         |
| ------------ | --------------------------------------------------------------- |
| Soniya Akter | https://github.com/soniya-builds                                |
| LinkedIn     | https://www.linkedin.com/in/mstsoniyaakter/                     |
| Email        | [soniya.akter1805@gmail.com](mailto:soniya.akter1805@gmail.com) |

---

## License

This project is released under the MIT License.