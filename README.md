# Bayesian metamodeling tutorial

## [![License: GPL v2](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)

Click [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tanmoy7989/bayesian_metamodeling_tutorial.git/master) to launch the tutorial. *If you are opening this link for the first time, allow up to 15 minutes to launch.*

## Overview

This tutorial is supplementary to the manuscript [Bayesian metamodeling: divide-and-conquer modelng of complexg representations](www.pnas.org). *Metamodeling* is an unique probabilistic framework that may couple different simulation models at different length and time scales (and of different representations) to study the inter-dependency of the parameters and degrees of freedom of each model. As a candidate system for applying this novel methodology, we look at the process of coupling different models of the pancreatic beta-cell to develop a harmonized insight into cellular processes. In principle this framework should allow us to couple models of the cell that are very different from each other, e.g. pharmacokinetic models vs. molecular simulation models and the coupling framework should be agonistic to the spatio-temporal scale separations between the input models. While we aren't quite there yet, we present an implementation of metamodeling using toy models of the pancreatic beta cell. 

The framework is powered by the probabilistic programming language [PyMC3](https://docs.pymc.io) (version 3.8)

## Contents

The ``mm`` directory contains the backend which includes a thin wrapper over PyMC3, distributed over various modules in the ``mm/core`` subfolder. Input models are specified as Python function kept in the ``mm/models`` subfolder. The ``mm/experiments`` subfolder contains scripts for running experiments with different types of coupling imposed on two or more input models. Data and parameter sets used for said experiments can be found in the ``mm/datasets`` subfolder and the ``mm/default_params.json`` file. 

## Tutorial

The jupyter notebook ```index.ipynb``` contains a small tutorial that takes you step-by step from building probabilistic models, to coupling them and eventually a live demonstration of coupling two simple models relevant to beta cell biology. The tutorial should take 20-30 mins to complete. If you have questions or confusion regarding the tutorial material, please feel free to raise an issue on github or reach out to me directly at ``tsanyal [at] salilab [dot] org``. 

Data and parameters used to run the notebook can be found in ```datasets```. The file ``tutorial_utils.py`` is a collection of some commonly used boilerplate code throughout the tutorial notebook. To launch a binder image of this repository and interact with the notebook directly from your browser, please click the ```launch tutorial``` badge above. Please allow ~ 15 mins for the server to launch for the first time. Binder employs efficient caching so that when for future launches, it should be relatively fast.  

## Installation

Clone the repository locally and follow the documentation in the code itself to run the experiments. Please make sure to install all necessary python dependencies (preferably through anaconda, but pip will work too) listed in the ``environments.yml`` file and third-party softwares listed in ``apt.txt`` (in this case just the graphviz package).