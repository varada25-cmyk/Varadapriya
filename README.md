# special-sniffle
# Modularity-Based Community Detection in the Karate Club Network

## Overview

This project implements **spectral modularity-based community detection** on the Zachary Karate Club network using Python.

The main objective is to identify communities within a social network by analysing the connections between individuals. The project uses the modularity matrix, eigenvalues, and eigenvectors to divide the network into smaller communities through recursive spectral bisection.

It also investigates how the importance and structural roles of individual nodes change as the network is progressively divided.

## Objectives

- Understand and implement modularity-based community detection.
- Construct the adjacency matrix and modularity matrix.
- Use eigenvalue and eigenvector analysis to identify community divisions.
- Implement recursive spectral bisection.
- Compare the detected communities with the actual historical division of the Karate Club.
- Analyse node properties using centrality measures and clustering coefficients.
- Compare the standard restricted modularity method with Newman's generalized method.

## Methodology

### 1. Network Construction
The Karate Club graph is loaded using NetworkX. It contains 34 nodes and 78 edges, representing individuals and their connections.

### 2. Modularity Matrix
The modularity matrix is constructed using:

\[
B=A-\frac{kk^T}{2m}
\]

where:
- \(A\) is the adjacency matrix.
- \(k\) is the vector of node degrees.
- \(m\) is the total number of edges.

### 3. Spectral Community Detection
Eigenvalue and eigenvector analysis is performed on the modularity matrix. The leading eigenvector is used to divide nodes into two groups based on the signs of its components.

### 4. Recursive Bisection
The splitting procedure is repeated on the resulting communities until no further acceptable split is found.

### 5. Modularity Evaluation
The modularity score is calculated to evaluate the quality of the detected community structure. The implementation is also compared with NetworkX's independent modularity calculation.

### 6. Node-Level Analysis
Four network measures are calculated after each partition:

- Degree Centrality
- Betweenness Centrality
- Closeness Centrality
- Clustering Coefficient

These measures help examine how node importance and connectivity patterns change as the network is divided.

### 7. Comparison of Methods
The standard restricted modularity approach is compared with Newman's generalized modularity method to investigate differences in the resulting communities.

## Results

- The first spectral division separates the network into groups of 16 and 18 nodes.
- The first division correctly matches the actual historical faction labels for 33 out of 34 nodes.
- The standard recursive bisection method identifies 5 final communities.
- The final modularity score is approximately **0.4094**.
- The generalized method also identifies 5 communities, but produces a different partition.
- The evolution of node centrality and clustering measures is visualized across the successive iterations.

## Visualizations

The notebook generates the following visualizations:

- `partitions.png` – Community structure at each iteration.
- `metric_evolution.png` – Changes in node-level network metrics across iterations.

## Technologies Used

- Python
- NumPy
- NetworkX
- Matplotlib
- Pandas
- Jupyter Notebook

## How to Run

1. Clone or download this repository.
2. Install the required libraries:

   ```bash
   pip install numpy networkx matplotlib pandas jupyter
   ```

3. Open the Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

4. Run `karate_modularity.ipynb` cell by cell.

No external dataset is required because the Karate Club graph is available directly through NetworkX.

## References

1. M. E. J. Newman, "Finding community structure in networks using the eigenvectors of matrices," *Physical Review E*, 74, 036104, 2006.
2. W. W. Zachary, "An Information Flow Model for Conflict and Fission in Small Groups," *Journal of Anthropological Research*, 33(4), 452–473, 1977.

---

**Project:** Modularity-Based Community Detection in the Karate Club Network  
**Course:** DSC212 – Graph Theory Module
