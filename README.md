# MLDatasets.jl
[![Build Status](https://travis-ci.org/hshindo/MLDatasets.jl.svg?branch=master)](https://travis-ci.org/hshindo/MLDatasets.jl)

`MLDatasets` provides an access to common machine learning datasets for [Julia](http://julialang.org/).  
Currently, julia 0.5 is supported.

The datasets are automatically downloaded to the specified directory.  
The default directory is `MLDatasets/datasets`.

## Installation
```julia
julia> Pkg.clone("https://github.com/hshindo/MLDatasets.jl.git")
```

## Basic Usage
```julia
using MLDatasets

train_x, train_y = MNIST.traindata()
test_x, test_y = MNIST.testdata()
```
Use `traindata(<directory>)` and `testdata(<directory>)` to change the default directory.

## Available Datasets
### CIFAR-10
The [CIFAR-10](https://www.cs.toronto.edu/~kriz/cifar.html) dataset consists of 60000 32x32 color images in 10 classes.

### CIFAR-100
The [CIFAR-100](https://www.cs.toronto.edu/~kriz/cifar.html) dataset consists of 600 32x32 color images in 100 classes.  
The 100 classes are grouped into 20 superclasses (fine and coarse labels).

### MNIST
The [MNIST](http://yann.lecun.com/exdb/mnist/) dataset consists of 60000 28x28 images of handwritten digits.

### PTBLM
The PTBLM dataset consists of Penn Treebank sentences for language modeling, available from [tomsercu/lstm](https://github.com/tomsercu/lstm).  
The unknown words are replaced with `<unk>` so that the total vocaburary size becomes 10000.  
Plus, the special word: `<EOS>` is added to the end of each sentence.

## Data Size
| | Type | Train x | Train y | Test x | Test y |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **CIFAR-10** | image | 32x32x3x50000 | 50000 | 32x32x3x10000 | 10000 |
| **CIFAR-100** | image | 32x32x3x500 | 2x500 | 32x32x3x100 | 2x100 |
| **MNIST** | image | 28x28x60000 | 60000 | 28x28x10000 | 10000 |
| **PTBLM** | text | 42068 | 42068 | 3761 | 3761 |

## Contributors
* [hshindo](https://github.com/hshindo)
* [goto-keisuke](https://github.com/goto-keisuke)
