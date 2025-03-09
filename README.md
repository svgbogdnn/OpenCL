# BitonicSort on OpenCL

This repository demonstrates how to use OpenCL to sort an array in parallel using the Bitonic Sort method in C++. The code illustrates the main steps of working with OpenCL - from initializing the platform and device to reading the results back to the host.

- **Bitonic Sort**
A parallel sorting method in which the array is split into pairs at each stage, which are sorted among themselves. This process is repeated in several stages until the entire array is sorted.

- **OpenCL**
An open standard for parallel computing on various types of devices (CPU, GPU, etc.). In this example, it is used to parallelize the operation of comparing and swapping array elements.

- **Main steps:**
1. **OpenCL initialization**
- Getting a list of available platforms and choosing one of them.
- Get devices (e.g. CPU/GPU), create context and command queue.
2. **Load and compile kernel**
- Read kernel source from `BitonicSort.cl` file.

- Create `cl::Program` object and compile for selected device.
3. **Prepare data**
- Read array from standard input.

- Create OpenCL buffer and copy source data to it.
4. **Run kernel**
- Set kernel arguments: data array, current stage and pass number.
- Call `enqueueNDRangeKernel` multiple times for each stage of bitonic sort.
5. **Read result**
- Copy sorted data from buffer back to host memory.
- Write results to standard output.