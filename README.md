<h1 align="center">VoxProg<br>3D Spatial Reasoning through Voxel Programming</h1>

<p align="center">
  <a href="https://github.com/zhichao-zhai">Zhichao Zhai</a><sup>1</sup> ·
  Menglei Zhao<sup>1</sup> ·
  Guikun Chen<sup>1</sup> ·
  Zihao Yan<sup>2</sup> ·
  Kanzhi Wu<sup>2</sup> ·
  Wenguan Wang<sup>1</sup> ·
  Jun Xiao<sup>1</sup>
</p>
<p align="center">
  <sup>1</sup>Zhejiang University &nbsp;&nbsp;
  <sup>2</sup>vivo Mobile Communication Co., Ltd., Shenzhen, China
</p>

<p align="center">
  <img src="https://img.shields.io/badge/arXiv-Coming%20soon-B31B1B?style=for-the-badge&logo=arxiv&logoColor=white" alt="arXiv — coming soon">
  <a href="https://voxprog.github.io/"><img src="https://img.shields.io/badge/Project%20Page-Website-3d7276?style=for-the-badge" alt="Project website"></a>
  <a href="https://voxprog.github.io/#qualitative-results"><img src="https://img.shields.io/badge/Explore-Interactive%20Results-2b4f5c?style=for-the-badge" alt="Explore interactive results"></a>
</p>

<p align="center">
  <b>Turning natural-language instructions into executable programs that reason over 3D geometry.</b>
</p>

<p align="center">
  <a href="https://voxprog.github.io/"><img src="docs/figures/current/teaser.png" alt="VoxProg solves diverse 3D object-placement tasks through voxel programming" width="100%"></a>
</p>

## Overview

**VoxProg** enables VLM coding agents to solve open-ended 3D spatial tasks through **voxel programming**. Given an instruction and a scene, the agent writes Python programs that inspect object geometry, construct the spatial references needed for the task, and compute a 6-DoF placement pose. Visual and numerical feedback lets it refine both geometric selections and object placements.

The central idea is to expose local mesh surfaces as regular 3D grids that programs can inspect with array operations. An instruction such as *“place the plate upright in the rack”* becomes a concrete geometric procedure: find the dividers and support rails, construct the receiving slot, then align and seat the plate within it.

## How it works

<p align="center">
  <img src="docs/figures/current/pipeline.png" alt="VoxProg pipeline: task interpretation, evidence programming, and pose programming with execution feedback" width="100%">
</p>

1. **Interpret and ground.** Decompose the instruction into geometric references and locate visual anchors on the scene meshes.
2. **Construct geometric evidence.** Generate programs over local voxel views to select task-relevant surfaces, boundaries, and regions; inspect and refine these selections using execution feedback.
3. **Solve the placement.** Generate a pose program that measures the selected geometry and computes the object's rigid transformation, then refine it with rendered observations and contact or clearance diagnostics.

## VoxProg-Bench and results

**VoxProg-Bench** contains 71 open-ended placement tasks spanning functional use, geometric fit, and contextual arrangements. Evaluation pairs **Intent Alignment** with **3D Physical Validity**, assessing whether a placement follows the instruction and is physically plausible.

We compare VoxProg with relation-based, keypoint-based, and mesh-based approaches, and additionally evaluate on **RoboCasa** and **Open6DOR v2**. The project page includes quantitative results and 15 interactive case comparisons, with views for Reference, Direct Mesh Placement, GenManip, GenSim2-kPAM, and VoxProg.

<p align="center">
  <a href="https://voxprog.github.io/#results"><b>View quantitative results</b></a>
  &nbsp; · &nbsp;
  <a href="https://voxprog.github.io/#qualitative-results"><b>Browse interactive comparisons</b></a>
  &nbsp; · &nbsp;
  <a href="https://voxprog.github.io/#external-evaluation"><b>Explore external evaluations</b></a>
</p>

## Release status

This is the official project repository for **VoxProg**. The project website is available now. The arXiv link and citation will be added when the paper becomes public; research code will be released upon acceptance.
