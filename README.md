Code and Data supporting 

Strongly resonant polarization dynamics of pulse trains in a spin-flip model for an excitable microlaser with delayed self-feedback 
S. Ruschel, S. Barbay, N. G. R. Broderick, B. Krauskopf 
arXiv: 2508.13630
https://arxiv.org/abs/2508.13630

-------------------------------------------------------------------------------

Overview
--------

This repository contains Matlab and Python code, as well as the data used to generate the results and figures in the paper. 
Most data is already precomputed, but some large files need to be reassembled before use.

The project combines:
- Matlab (R2018a) scripts for numerical continuation and figure generation using DDE-BifTool.
- Python (2.7) scripts (using pydelay) for time-domain simulations that generate data for the Matlab continuation analysis.

-------------------------------------------------------------------------------

Requirements
------------

- Matlab R2018a (or newer)
- Python 2.7
- Python packages: pydelay, numpy, matplotlib
- DDE-BifTool (latest version from https://github.com/DDE-BifTool/DDE-Biftool)

Please make sure to edit the Matlab scripts so that they point to the correct folder where DDE-BifTool is installed, or clone DDE-BifTool repository when working in Github desktop.

-------------------------------------------------------------------------------

Reassembling the Data
---------------------

Some data files are split due to GitHub size limits. Please reassemble them before running the plotting scripts.

1. In MatlData, open Matlab and run:
   reconstruct_mat_from_parts('BranchData_parts','BranchData.mat')

2. In pythonData, open Matlab and run:
   reassemble_txts_list()

After this step, all data files will be ready for plotting.

-------------------------------------------------------------------------------

Reproducing the Figures
-----------------------

The files PlotFig*.m create the panels of Figures 1–5 in the paper. 
To generate the figures, open Matlab and run:

   - PlotFig1
   - PlotFig2
   - PlotFig3
   - PlotFig4
   - PlotFig5

Each script automatically loads the corresponding precomputed data.

-------------------------------------------------------------------------------

Numerical Continuation
----------------------

The files ComputeFig*.m contain the Matlab code used for numerical continuation of solution branches. 
To recompute these computations, use:

   - ComputeFig2
   - ComputeFig3
   - ComputeFig4
   - ComputeFig5

These require DDE-BifTool to be in your Matlab path.

-------------------------------------------------------------------------------

Python Simulations
------------------

Python scripts for numerical simulations are located in the pythonData folder. 
They use pydelay to generate time series data for use in Matlab.

Example workflow:

   - cd pythonData/Slice_epsp0022
   - python polar_det_period.py     # Identify period
   - python polar_gen_psol.py       # Generate and save periodic solution data
   - python PolarMaxPeakes.py       # Compute maximum peak data

The resulting .txt files can then be imported into Matlab for continuation and plotting.

-------------------------------------------------------------------------------

Citation
--------

If you use this code or data, please cite:

S. Ruschel, S. Barbay, N. G. R. Broderick, B. Krauskopf (2025).
"Strongly resonant polarization dynamics of pulse trains in a spin-flip model for an excitable microlaser with delayed self-feedback."
arXiv: 2508.13630

-------------------------------------------------------------------------------

Contact
-------

S. Ruschel
https://github.com/stefanruschel
