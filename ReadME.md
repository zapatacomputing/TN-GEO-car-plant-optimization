A public repository for storing the data presented in "Quantum-Inspired Optimization for Industrial Scale Problems"

## What is it?

This repository contains data gathered when benchmarking TN-GEO vs a set of conventional solvers (GA1, GA2, GAU, PT, SAB) for two different parameterizations (3-body and 12-body) of the BMW production planning problem. Please see : <url> for more details and explanations.

## Structure of directories

Here is a tree structure of the directories in this repository:
``` bash
├── data
│   ├── 3body
│   │   ├── conventional_optimizers
│   │   └── GEO
│   │       ├── MPS_bond5
│   │       ├── MPS_bond6
│   │       ├── MPS_bond7
│   │       └── MPS_bond8
│   └── 12body
│       ├── conventional_optimizers
│       └── GEO
│           └── MPS_bond6
└── README.md
```
In the data directory, there are two subdirectories, one for each parameterization of the problem. For each parameterization, there are two subdirectories, one containing the results of conventional optimizers and the other one containing the results of GEO. The GEO directories contain different subdirectories of the format `{type of tensor network}_bond{maximum bond dimension}`. In this project, we benchmarked Matrix product states(MPS) with bond dimensions between 5 to 8.

## File formats and naming

All data files are in `.json` format with the following naming conventions:

- For 3-body, conventional_optimizers: 
    `result_margin{size of margin}_{name of conventional optimizer}_{rate deviation option}.json`
- For 3-body, GEO: 
    `result_margin{size of margin}_{type of encoding}_TNGEO_{name of conventional optimizer}_{rate deviation option}.json`
- For 12-body, conventional_optimizers
    `result_{name of conventional optimizer}__{rate deviation option}.json`
- For 12-body, GEO:
    `result_TNGEO_{name of conventional optimizer}_{rate deviation option}.json`

## File contents

Each file contains a dictionary with the following keys:

- "random_seeds" : a list containing random_seeds used to initialize the solver in each run

- "optimal_costs" : a list containing best costs attained in each run

- "optimal_solutions" : a list containing best solutions attained in each run

- "cost_history" : a list of lists containing cost history of each run

- "solution_history" : a list of lists containing solution history of each run

- "duration": a list containing the duration of each run


