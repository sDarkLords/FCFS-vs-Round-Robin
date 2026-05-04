# FCFS-vs-Round-Robin

This project is a process scheduling simulator that compares two fundamental CPU scheduling algorithms:

- FCFS (First Come First Served)
- Round Robin (with time quantum)

The simulation generates processes dynamically, executes both algorithms, and evaluates their performence using scheduling metrics such as:

- Waiting time
- Turnaround time
- Average performance

---

## Table of Contents

- [Problem Statement](#problem-statement)
- [Algorithms Explained](#algorithms-explained)
- [System Architecture](#system-architecture)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Example Output](#example-output)
- [Performance Metrics](#performance-metrics)
- [Intelligent Scalling Features](#intelligent-scalling-features)

---

## Problem Statement

In operating systems, the schedular must decide:

**Which process gets CPU time and for how long?**

Different scheduling strategies impact:

- system responsiveness
- fairness
- performance

---

## Algorithms Explained

### FCFS (First Come First Served)

- Processes executed in arrival order
- Non-preemptive
- Simple but inefficient for long jobs

Pros:

- Easy to implement
- Low overhead

Cons:

- Convoy effect
- Poor responsiveness

---

### Round Robin

- Each process gets a fixed time quantum
- Preeemtive scheduling
- Fair CPU sharing

Pros:

- Better responsiveness
- Fair scheduling

Cons:

- Context switching overhead
- Depends on quantum size

---

## System Architecture

The project is modular and consists of:

### Input Module 

- Validates number of processes

### Data Generator

- Generates:
  - Process IDs (P1, P2, ...)
  - Random burst time

### Scheduling Engine

- FCFS Implementation
- Round Robun Implementation

### Metrics Engine

- Waiting time
- Turnaround time
- Averages

### Output Layer

- Console output (formatted tabels)
- File export (`simulation_results.txt`)

---

## Requirements

- Bash (Linux / macOS / WSL on Windows)
- `bc` (optional, for percentage calculations)

Install `bc` if needed:

```bash
sudo apt install bc
```

---

## Installation

Clone the repository

```bash
git clone https://github.com/cybhermes/FCFS-vs-Round-Robin.git
cd FCFS-vs-Round-Robin
```

Make the script executable

```bash
chmod +x FCFSvsRoundRobin.sh
```

## Usage

Run the script

```bash
./FCFSvsRoundRobin.sh
```

The program ask for number of processes (total processes to simulate)

---

## Example Output

```bash
Process | Burst | Waiting | Turnaround
--------|-------|---------|-----------
P1      | 5     | 0       | 5
P2      | 3     | 5       | 8
P3      | 2     | 8       | 10
```

---

## Performance Metrics

The simulation calculates:

- Waiting Time -> time a process waits before execution
- Turnaround Time -> total time from arrival to completion
- Average Waiting Time
- Average Turnaround Time

## Intelligent Scalling Features

Implementation includes:

Adaptive Output
- Detailed logs for <= 20 processes
- Summary-only for large inputs

Large Dataset Handling
- Partial output for > 50 precesses
- Prevents terminal flooding
