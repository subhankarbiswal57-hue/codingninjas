# AIML Recruitment 2026 — Subhankar

## Candidate Details
- **Name:** Subhankar
- **Institution:** SRM Institute of Science and Technology, Kattankulathur
- **Program:** B.Tech CSE (AI & ML), 2nd Year

## Tasks Completed
- **Task 2: Neural Network (MNIST Digit Classification)**

## Problem Statement
Build and train a simple neural network to classify handwritten digits (0–9) from the
MNIST dataset, understand the role of each network component (layers, activations),
and analyse how changing a hyperparameter affects performance.

## Approach
1. Loaded and inspected the MNIST dataset (60,000 train / 10,000 test images, 28×28 grayscale).
2. Normalized pixel values to [0, 1] and flattened images to 784-length vectors.
3. Built a simple feed-forward neural network: Input → Dense(128, ReLU) → Dense(64, ReLU) → Dense(10, Softmax).
4. Trained the model using the Adam optimizer and sparse categorical crossentropy loss, tracking training/validation loss and accuracy.
5. Evaluated the model on the test set using accuracy, a confusion matrix, and a classification report (precision/recall/F1).
6. Ran an experiment by changing the hidden layer size and compared results against the baseline model.

## Technologies Used
- Python
- TensorFlow / Keras
- NumPy
- Matplotlib
- Seaborn
- scikit-learn

## Results
- Baseline model test accuracy: see `results/metrics.json` and notebook output.
- Confusion matrix shows most confusion between visually similar digits (e.g. 4/9, 3/5).
- Experiment (modified hidden layer size) results and comparison are shown in the notebook and `results/experiment_comparison.png`.

## Key Learnings
1. Normalizing input data significantly stabilizes and speeds up neural network training.
2. ReLU avoids the vanishing gradient problem common with sigmoid/tanh in deeper networks, while Softmax is well suited for multi-class output since it produces a proper probability distribution over classes.
3. Model capacity (number of neurons/layers) directly trades off between underfitting and overfitting — more neurons improved fit but increased overfitting risk on this simple dataset.

## Challenges
- **Challenge:** Deciding how to evaluate whether the model was overfitting or underfitting.
- **Solution:** Plotted training vs validation loss/accuracy curves across epochs — a widening gap between training and validation curves confirmed overfitting, which guided the choice of hyperparameter to experiment with.

## Repository Structure
```
AIML-Recruitment-2026-Subhankar/
├── README.md
├── requirements.txt
├── notebooks/
│   └── task2_mnist_neural_network.ipynb
├── results/
│   ├── training_curves.png
│   ├── confusion_matrix.png
│   ├── experiment_comparison.png
│   └── metrics.json
└── models/
    └── mnist_model.h5
```
