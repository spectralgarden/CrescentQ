```========================================================================
                     SPECTRAL GARDEN — CRESCENTQ
========================================================================

Ethereal Phase Equalizer • 24‑Band Precision • Linear/Minimum Phase Modes
Built with JUCE 8+ • VST3 / AU / Standalone

========================================================================

CrescentQ is a high‑precision 24‑band parametric equalizer designed for mixing,
mastering, and surgical spectral shaping. It features switchable minimum‑phase
and linear‑phase architectures, per‑band Mid/Side routing, multi‑stage
oversampling, and real‑time FFT visualization. The engine is optimized for
low‑latency operation while offering advanced phase‑coherent processing for
critical audio work.

This document provides a complete overview of CrescentQ’s architecture,
controls, and build environment.
========================================================================

1. CORE ARCHITECTURE & FEATURES
========================================================================

[1] 24‑Band Parametric Array
    • Up to 24 fully independent filter bands
    • Filter types:
        Bell, Low Shelf, High Shelf, Low Cut, High Cut, Notch, Bandpass
    • Per‑band routing:
        Stereo, Left, Right, Mid, Side
    • Logarithmic frequency mapping (20 Hz → 20 kHz)

[2] Phase & Oversampling Engine
    • Minimum‑phase and linear‑phase modes
    • Linear‑phase mode includes automatic latency reporting (1024 samples)
    • Oversampling tiers:
        1x, 2x, 4x, 8x
    • Eco Mode:
        Reduces CPU load during large sessions

[3] Visualization & Analysis
    • Dual FFT analyzers (input/output)
    • Real‑time EQ curve rendering
    • Stereo peak meters
    • Internal CPU performance monitor

[4] Workflow & Presets
    • A/B comparison banks (stateA / stateB)
    • 25 factory presets across mixing, mastering, vocals, surgical, creative
    • User preset system:
        JSON‑backed `.coven` files stored in local application directories

========================================================================

2. PARAMETER CONTROL REFERENCE
========================================================================
Global Controls
    • global_bypass      — Boolean
    • global_gain        — −30 dB → +30 dB
    • linear_phase       — Boolean
    • oversampling       — 1x / 2x / 4x / 8x
    • eco_mode           — Boolean

Band Controls (0–23)
    • band_X_active      — Boolean
    • band_X_type        — Filter topology
    • band_X_frequency   — 20 Hz → 20 kHz
    • band_X_gain        — −30 dB → +30 dB
    • band_X_q           — 0.10 → 36.00
    • band_X_mode        — Stereo / L / R / Mid / Side

========================================================================

3. SYSTEM REQUIREMENTS
========================================================================

Framework:
    JUCE 8+

Formats:
    VST3, AU, Standalone

Supported OS:
    Windows, macOS

========================================================================

4. BUILDING FROM SOURCE
========================================================================

1. Place CrescentQ source files inside a JUCE project directory.
2. Open the `.jucer` project using Projucer.
3. Configure exporter targets (Xcode / Visual Studio).
4. Build in Release mode for optimal FFT and oversampling performance.

========================================================================

LICENSE
========================================================================

Copyright © 2026 Spectral Garden.
All rights reserved.

========================================================================

END OF DOCUMENT
==============================================================================



