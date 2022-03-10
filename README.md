#  Benchmarking GEMM (on Intel® Architecture Processors)

https://www.intel.com/content/www/us/en/developer/articles/technical/benchmarking-gemm-with-intel-mkl-and-blis-on-intel-processors.html

To build the Intel® MKL version:

```
make mkl
```

To build the BLIS* framework version:

```
make blis
```

To build both the Intel® MKL and BLIS* framework versions:

```
make all
```

Running the make command as shown above will create the corresponding executables in the current folder (sgemmbench.mkl, dgemmbench.mkl, sgemmbench.blis, dgemmbench.blis).

The run-script runs the GEMM benchmark with a specified number of threads, problem size, and math library.

```
./run.sh <NUM_THREADS> <SIZE_N> <MATH_LIBRARY>
```

Where:

NUM_THREADS: Number of threads to run the benchmark with. For example for a dual socket Intel® Xeon® Gold 6148 with a total of 40 cores, you can select "40". The script would use the correct affinity (1 thread per core).
SIZE_N: The problem size with which to run the benchmark (e.g., 10000). If you want to run with a range of preselected values, you can use the word "all".
MATH_LIBRARY: Here you can select "mkl" for the Intel® MKL or "blis" for BLIS* framework.

Examples:

Run with 20 threads, use all the predefined problem sizes, and use the Intel® MKL version of GEMM.

```
./run.sh 20 all mkl
```

Run with 28 threads, use a problem size with 10000x10000 matrix, and use the BLIS* framework version of GEMM.

```
./run.sh 28 10000 blis
```