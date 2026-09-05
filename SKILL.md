---
name: img2threejs
description: Turn an object or character reference image into a quality-gated, animation-ready procedural Three.js model. Use for image-to-3D reconstruction and detail-accurate procedural model work; do not use to claim fidelity from an unsupported reference.
---

# img2threejs

Build a procedural Three.js model that is faithful to the supplied visual evidence. Start each run with `python forge/state.py init --state .img2threejs/state.json`, then run `python forge/next.py --state .img2threejs/state.json <sculpt-spec>` before visual analysis, spec/build/probe, render and review. See `grimoire/build/` for state fields and commands.

## Canonical flow

1. Record source, target, constraints and missing views in the state/spec.
2. Analyse visible silhouette, proportions, materials and feature hierarchy before scripting geometry.
3. Build from the approved spec with deterministic seeds and explicit parts.
4. Capture the required views and run deterministic geometry/render gates.
5. Use visual review for semantic fidelity that scripts cannot measure; record the decision and return to state before another correction.

Deterministic scripts measure gates and evidence. They do not decide semantic likeness. A failed hard gate, unsupported family, missing essential view or correction bound stops or requests input; it is not papered over by a global score.

## CS2 scope

The supported CS2 path is **knife-only**, using weapon-v1.4, `manifestSchema: 1`, adapter `cs2-knife-v1` and review `cs2-knife-review-v1`. Pistol, Glock-18, rifle, SMG, sniper, heavy, glove and unknown knife subtype requests stop as unsupported. Do not select a generic fallback.

For a CS2 knife, read `grimoire/intake/cs2_intake_contract.md`, `grimoire/review/gates_reference.md` and `grimoire/review/self_correction.md` before advancing. Preserve classification evidence, intake manifest, component contract, deterministic review and the versioned knife review scene.

## Progressive references

- `grimoire/intake/` — classification, source and intake contract.
- `grimoire/review/` — deterministic gates, visual review and correction guidance.
- `grimoire/build/` — procedural build and runtime evidence.
- `skills/` — narrow task profiles, read only the profile selected by the supported route.

The skill modifies no adapter or runtime contract merely to admit a new item family. A family expansion needs explicit scope and its own validated implementation.
