# Cookiecutter Kaggle
**Attention: Work in Progress** 
_A logical, reasonably standardized, but flexible project structure for doing and sharing data science [kaggle](https://www.kaggle.com/) projects._

Based on the [template by driven-data](https://github.com/drivendata/cookiecutter-data-science). 

### News:

- The project will be presented and used at the [Berlin Kaggle Meetup Group](http://www.meetup.com/de-DE/Kaggle-Berlin/events/233522109/)

### Requirements
-----------
 - Python 2.7 or 3.5
 - [cookiecutter Python package](http://cookiecutter.readthedocs.org/en/latest/installation.html) >= 1.4.0: `pip install cookiecutter`
 - Optional: [Docker](https://www.docker.com)

### Usage:
------------
To initialize a new project after your system fulfills the requirements run:

    cookiecutter https://github.com/uberwach/cookiecutter-kaggle

You can build the Docker image (based on the Kaggle Python3 Docker image) via:

    docker build -t yourproject/tagname .

and then run an interactive shell via

   docker run -i -v $PWD:/tmp/working \
      -w=/tmp/working -t yourproject/tagname \
      /bin/bash

on Windows you would use %cd% (current directory) instead of $PWD (print working directory).

You are asked to input data such as the project name and other uses of, say, the license. A project with the following file structure is being generated:

    ├── LICENSE
    ├── Makefile           <- Makefile with commands that perform parts of the processing pipeline
    ├── README.md          <- The top-level README
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    ├── Dockerfile         <- Dockerfile, alternative approach to manage environment
    │                         more interesting if using non-Unix
    ├── submissions        <- Directory to keep submissions
    │
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions for submissions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
