# Ramon Veloso Vieira

Computer Engineering student in São Paulo, graduating December 2027. I work on the boundary between hardware and software — RTL on one side, C++ on ARM on the other.

**Currently looking for an embedded systems internship in São Paulo.**
ramonvelosovieira@gmail.com · [LinkedIn](https://www.linkedin.com/in/ramon-veloso-vieira/) · [LeetCode](https://leetcode.com/u/rappudo/)

---

### What I've been building

**Feature extraction RTL for the Salsa ASIC** — Iniciação Científica at Escola Politécnica, USP, advised by Prof. Dr. Bruno Sanches. Salsa is a readout chip for micro-pattern gaseous detectors, developed with IRFU/CEA Saclay and destined for the Electron-Ion Collider at Brookhaven National Laboratory.

I wrote the module that turns a 40 MHz ADC stream into physics: a Double Constant Fraction Discriminator for event timing, a matched-filter convolution for amplitude, and a 6-state FSM driving the output packet format — all synthesizable SystemVerilog for TSMC 65 nm. Verified under Verilator with a Python stimulus generator I built alongside it, across the full 50–500 ns peaking range and pileup at 16× nominal event rate.

The result I'm proudest of isn't the module itself. By decomposing where the residual amplitude error actually came from, I showed that moving pileup correction off-chip cuts the error from 10.0% to 3.7% for one added field in the output protocol — and then documented why that *still* might be the wrong call, since it strips corrected data from every downstream block on the die.

**[FaceGateway](https://github.com/rappudo/Embarcados-Projeto)** — facial recognition access control running entirely on a Raspberry Pi 4. I owned the C++17 edge pipeline: CSI capture, BlazeFace detection, eye-keypoint alignment, ArcFace embeddings through ONNXRuntime, and servo actuation over libgpiod.

I built a per-stage profiler before optimizing anything, which is how I know the idle loop runs at ~70 fps and a full recognition cycle takes 648 ms — of which 634 ms is ArcFace inference alone. We missed our 500 ms target. The profiler made the reason unambiguous, and the writeup says so.

Benchmarked against the 6,000 canonical LFW pairs: EER 3.22%. Production threshold is set well below the equal-error point, at FAR 0.0% / FRR 36.3% — for a door, letting the wrong person in costs more than making the right person try twice.

**[Drone route optimizer](https://github.com/rappudo/Drone-com-otimizador-de-rotas)** — genetic algorithm for multi-drone delivery routing in 3D under fuel and payload constraints, with long routes decomposed across parallel drones.

---

### Tools

`SystemVerilog` `Verilator` `C++17` `Python` `Rust` `libgpiod` `ONNXRuntime` `OpenCV` `CMake` `GoogleTest` `Linux` `MQTT` `PostgreSQL`

Also teach — undergraduate TA for Data Structures & Algorithms and for Programming Logic. Explaining pointer arithmetic to a first-year student is its own kind of debugging.
