# Teacher Axis: A Geometrically Distinct Direction in LLM Activation Space

Mechanistic interpretability experiments asking whether a "Teacher Axis" exists in LLM activation space, and whether it's the same direction as 
the RLHF-induced Assistant Axis or a different one.

This started as a side project after I couldn't get a Socratic tutoring app ([socratOS](link)) to stop giving away homework answers. Ended up 
running activation steering experiments on Gemma 2B and Mistral 7B on free Kaggle compute.

---

## Findings

The Teacher Axis is near-orthogonal to the Assistant Axis (cosine ~0.0 to -0.2 across layers, replicated on both models), encodes pedagogical 
intent as a single holistic direction rather than a collection of separate behaviors, and causally improves Socratic outputs 2.3x under 
activation steering.

Full writeup on LessWrong: [link]

---

## What's Here

| File | Description |
|------|-------------|
| `teacher_axis_complete.ipynb` | Full experiment — axis derivation, steering sweep, sub-axis decomposition, prompt robustness check, Mistral 
replication |

Llama 3.1 8B replication was attempted but hit Kaggle GPU quota limits mid-run and is not in the results.

---

## Reproduce

All experiments run on a free Kaggle P100 (16GB VRAM). Total cost: $0.
```bash
pip install transformer_lens einops
```

Models loaded from HuggingFace: `google/gemma-2-2b`, `google/gemma-2-2b-it`, `mistralai/Mistral-7B-v0.1`, `mistralai/Mistral-7B-Instruct-v0.1`

---

## About

I'm a quant dev, not a researcher. I wrote this up on LessWrong because I wanted feedback from people who know what they're talking about. 
If something here is broken or interesting, issues and comments are open.
