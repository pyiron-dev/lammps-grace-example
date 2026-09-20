# LAMMPS + GRACE example

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/pyiron-dev/lammps-grace-example/main?labpath=01_lammps_grace_with_lammpsparser.ipynb)
[![Test notebooks](https://github.com/pyiron-dev/lammps-grace-example/actions/workflows/test-notebooks.yml/badge.svg)](https://github.com/pyiron-dev/lammps-grace-example/actions/workflows/test-notebooks.yml)

Two notebooks showing how to run the [GRACE](https://gracemaker.readthedocs.io/en/latest/gracemaker/tutorials/#132-lammps)
universal machine-learning potentials in LAMMPS (`pair_style grace/fs`, the native evaluator built into the
conda-forge `lammps=2025.07.22=*_5` package):

- [`01_lammps_grace_with_lammpsparser.ipynb`](01_lammps_grace_with_lammpsparser.ipynb) - via
  [`lammpsparser`](https://lammpsparser.readthedocs.io/en/latest/example.html) (file-based, `pyiron`-style interface).
- [`02_lammps_grace_with_pylammpsmpi.ipynb`](02_lammps_grace_with_pylammpsmpi.ipynb) - via
  [`pylammpsmpi`](https://pylammpsmpi.readthedocs.io/en/latest/) (interactive `mpi4py`-driven LAMMPS library).

Click the Binder badge above to run them in the browser, no local install required. To run locally instead:

```bash
conda env create -f environment.yml
conda activate lammps-grace-example
jupyter lab
```

`environment.yml` fully pins every dependency; [`.github/workflows/test-notebooks.yml`](.github/workflows/test-notebooks.yml)
runs both notebooks with `papermill` on every push/PR and weekly, so upstream releases that break the example are caught quickly.
