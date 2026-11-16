# LLM & Video AI VRAM Requirements Guide

A curated guide for matching local AI models to hardware. If you need precise calculations for context windows, KV-cache, and throughput, use the interactive calculator below.

### 🚀 Interactive Calculator
**[👉 Launch VRAMCalc (Zero-Tracking & Static)](https://vramcalc.sgl-00.workers.dev/)**

---

### Quick Reference: VRAM vs. Model Class
| Model Type | Recommended VRAM | Example Models |
| :--- | :--- | :--- |
| **Small (Chat/Coding)** | 8GB - 12GB | Qwen2.5-7B, Llama-3.1-8B |
| **Medium (Complex/MoE)** | 16GB - 24GB | Qwen3-32B, DeepSeek-R1-Distill |
| **Large (Production)** | 32GB - 48GB | Qwen3.8-Flash-Next (IQ3), Llama-4-70B |
| **Vision & Video** | 48GB+ | Flux.1, HunyuanVideo, Wan 2.1 |

*Note: Context window and KV-cache precision (FP16 vs Q8/Q4) will significantly increase requirements.*

### Why is this calculator different?
Unlike standard `params * bits` estimates, this tool factors in:
- **3-Layer Memory Engine**: Weight quantization + GQA/MLA context overhead.
- **Concurrent Serving**: Batch serving logic for vLLM/SGLang.
- **Throughput Estimates**: Bandwidth-bound token generation (`tok/s`).

---

### How to use
1. **Model Finder**: Match your current GPU VRAM to the best-performing models.
2. **Buy vs. Rent**: Calculate the break-even point for buying local hardware vs. renting cloud GPUs (Vast.ai / RunPod).
3. **CLI Generator**: Get ready-to-run commands for Ollama, llama.cpp, and vLLM.

---
*Maintained by the VRAMCalc community. Check out the [official calculator site](https://vramcalc.sgl-00.workers.dev/).*
