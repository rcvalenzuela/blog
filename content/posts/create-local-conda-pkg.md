---
title: "Building a local conda package"
date: 2020-04-08T21:30:12+02:00
tags: ["python", "conda"]
draft: false
---

## The process

1. Create the build files: meta.yaml, build.sh, build.bat. These files could be
located inside a conda directory in the same directory as the setup.py file
2. In the meta.yaml file the spurce/path parameter must be set to the relative path of the setup.py file.
3. If working in an environment different than root the location of the created package must be in the colda-bld directory of the environment and conda install may fail because it does not have the appropriate channel. In that case, the command:
    ````
    conda install -c ${CONDA_PREFIX}/conda-bld/ my_package
    ````
    might do the trick.

## Questions

What is a conda recipe?

## References

1. [Packaging Python projects](https://packaging.python.org/tutorials/packaging-projects/)
2. [Building Conda packages from scratch](https://docs.conda.io/projects/conda-build/en/latest/user-guide/tutorials/build-pkgs.html#)
