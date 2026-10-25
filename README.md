# Binary Iris Classification with Logistic Regression

A compact scikit-learn experiment that distinguishes Setosa from Versicolor and compares how different pairs of flower measurements affect classification accuracy.

## What this project explores

- Selecting feature columns and filtering a multiclass dataset into a binary problem.
- Creating a reproducible train/test split.
- Fitting and evaluating logistic regression.
- Comparing all six pairs of the four Iris features.

[logistic_regression.ipynb](logistic_regression.ipynb) starts with sepal length and petal length, then repeats the experiment for every feature pair. It uses scikit-learn's bundled Iris dataset and keeps 100 samples from classes 0 and 1, with 70 for training and 30 for testing (`random_state=42`).

## Results and limitations

The initial two-feature classifier correctly predicts **30 of 30 test samples (100%)**. All six feature pairs also reach 100% on this fixed binary test split.

These results apply only to the selected Setosa/Versicolor task and one small split. Virginica is excluded. The notebook does not perform cross-validation, scaling, hyperparameter search, or final evaluation on an additional untouched holdout. Comparing feature pairs on the same test set is exploratory, rather than an independent estimate after feature selection.

## Run it

Use Python 3.14.7, the version used for validation. From the repository root, create a virtual environment and install the direct dependencies.

Windows (PowerShell):

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

macOS/Linux:

```sh
python3 -m venv .venv
./.venv/bin/python -m pip install -r requirements.txt
```

Open the notebook in a Jupyter-compatible editor using that environment, restart the kernel, and run all cells in order. No external dataset download is needed.

In VS Code, open the notebook, choose **Select Kernel > Python Environments**, and select this repository's `.venv` interpreter. Other Jupyter-compatible editors should use the same interpreter.
