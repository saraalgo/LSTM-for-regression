# Using LSTM for regression prediction

**ONGOING WORK, NOT FINISHED!!!**

## About
1. The original repository was used for a company internal purpose, so what is presented here **is not replicable**, due to not being possible to share all the initial data used for this task.
2. This repository aims to serve as a **representation of an end-to-end ML pipeline using two approximations with LSTM models** to solve a **regression prediction**.
3. To enable its readability, it is already ran with the real data used.

## Purpose
The objective of this project was to calculate the **Total area planted** for the next year on each country of the US. That is why agronomy and weather data is used. For getting this values, four approximations have been tested and benchmarked:

1. Creating a **LSTM** model that predicts the output by each state, creating a model per each unique case.
2. Creating a **Autoencoder** + **LSTM** model that predicts the output by each state, creating a model per each unique case.
3. Creating a **LSTM** model with multioutput (one per each possible state), creating one single model for the whole country.
4. Creating a **Autoencoder** + **LSTM** model with multioutput (one per each possible state), creating one single model for the whole country.


## In case of reexecuting

Even though a new `data/00-raw/main.parquet` would be needed, if you are willing to do a synthetic replication, here are the steps to follow:

### Prerequisites

1. Install python 3.8

### Installation

1. Clone the repository in your personal device using the following command:

```sh
git clone https://github.com/saraalgo/LSTM-for-regression .git
```

2. Create and activate python environment if you do not count with the beforehand mentioned Python version. Otherwise, you could skip this step.

```sh
python3.8 -m venv LSTM-for-regression/
source bin/activate
```

3. Upgrade pip and install project requirements 
```sh
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```


## Project workflow

1. [Preprocess data](#1-preprocess-data)
    - [Load data to unify formats](#11-load-data-an-unify-formats)
    - [Get data to introduce to the model](#12-get-data-to-introduce-to-the-model)
    - [Outputs](#13-outputs)


### 1. Preprocess data
This is done in the folder `src/01-Preprocessing`.

#### 1.1 Load data an unify formats
In the [*Load-data.ipynb*](https://github.com/saraalgo/LSTM-for-regression/blob/main/01-Preprocessing/Load-data.ipynb) notebook is shown how the external data is loaded from the orignial formats and it is stored in the folder `data/01-Preprocessing`.

### 1.2 Get data to introduce to the model
Here in [*Preprocessing.ipynb*](https://github.com/saraalgo/LSTM-for-regression/blob/main/src/01-Preprocessing/Preprocessing.ipynb) the data to model in merged.

### 1.3 Outputs
In case of re-run it, the final data will be found in `data/01-Preprocessing/` as `data.pkl`.