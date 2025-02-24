# SilvaNet 🌟

Welcome to **SilvaNet**, a lightweight Python library designed to make deep learning concepts easy to grasp and apply. Whether you’re diving into neural networks for the first time or looking to streamline your educational tools, SilvaNet offers a simplified framework for constructing, training, and evaluating models. It’s intuitive, extensible, and an excellent resource for both beginners and advanced practitioners.

![SilvaNet](./ANN.png)

## 🚀 New Features & Upcoming Updates

- **Redesigned API**: We're currently redesigning SilvaNet's API to make it more familiar to PyTorch users. This change aims to offer a more intuitive interface for deep learning tasks.
  
- **CNN Layers (Numpy Implementation)**: Stay tuned for the addition of convolutional layers, all implemented purely in NumPy! Aiming to provide a deeper understanding of how convolutional operations work under the hood.

- **Notebooks for Exploration**: A set of Jupyter notebooks will be provided for further exploration. These will guide you through building models, training, and experimenting with various layers and functions.

## 🌟 Key Features

- **Autograd Support**: Effortlessly perform backpropagation with our autograd-enabled tensor class. This supports seamless gradient computation and simplifies model training.
  
- **Intuitive API**: Build neural networks easily with our user-friendly API. You can create, train, and evaluate models with minimal code. Our API is undergoing a redesign to offer better compatibility with PyTorch.

- **Element-wise Operations**: Perform basic element-wise operations such as addition, subtraction, and multiplication directly on tensors.

- **Activation Functions**: Use essential activation functions like Sigmoid, Tanh, and ReLU to introduce non-linearity into your models.

- **Loss Functions**: Implement popular loss functions such as Cross-Entropy for classification tasks, providing flexibility for model optimization.

- **Flexible and Extensible**: SilvaNet is highly customizable. You can create your own neural network architectures, add layers, experiment with different activation functions, and explore optimization algorithms.

- **Model Management**: Effortlessly save and load trained models. This makes it easy to reuse and share your models across different projects.

## 🚀 Getting Started

Here’s a quick example to get you started with SilvaNet:

```python
from autograd import Tensor
import numpy as np
from sklearn.datasets import load_breast_cancer
from sklearn.model_selection import train_test_split
from nn.Layers import Sequential, Dense
from nn.losses import CrossEntropyLoss
from nn.optimizer import SGD
from Network import NeuralNetwork

# Load Breast Cancer dataset
data = load_breast_cancer()
X = data.data
y = data.target

# Split the data into training and test sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Normalize features
X_train = X_train / np.max(X_train, axis=0)
X_test = X_test / np.max(X_test, axis=0)

# Define the neural network architecture
model = Sequential()
model.add(Dense(n_inputs=X_train.shape[1], n_units=64, activation='relu'))
model.add(Dense(n_inputs=64, n_units=32, activation='relu'))
model.add(Dense(n_inputs=32, n_units=2))  # Output layer without activation for binary classification

# Define loss function and optimizer
loss_fn = CrossEntropyLoss()
optimizer = SGD(parameters=model.get_parameters(), alpha=0.01)

# Create a neural network instance
nn = NeuralNetwork(model, loss_fn, optimizer)

# Compile the model
nn.compile(loss_fn, optimizer)

# Print model summary
nn.summary()

# Train the model
nn.fit(X_train, y_train, epochs=100, batch_size=16)

# Evaluate the model
nn.evaluate(X_test, y_test)
```

## ⚙️ Installation

To install **SilvaNet**, simply clone the repository:

```bash
git clone https://github.com/silvaxxx1/SilvaNet
cd SilvaNet
```

## 📚 Documentation

For detailed guides, installation instructions, and API references, check out our full [documentation](link-to-documentation).

## 🤝 Contributing

We welcome contributions from the community! If you have suggestions, bug reports, or want to help enhance SilvaNet, please review our [contributing guidelines](link-to-contributing-guidelines). We’re excited to collaborate with you!

## 📝 License

SilvaNet is licensed under the [MIT License](link-to-license). See the LICENSE file for more details.
