# Scientific Image Generation Workflow (Protocol-First Approach)

This repository documents the **Protocol-First Workflow** for generating physically and scientifically accurate images of complex laboratory experiments using AI (e.g., nanobanana pro, Midjourney, Stable Diffusion).

## The Problem
Standard text-to-image AI models fail at depicting scientific experiments accurately. They hallucinate floating equipment, incorrect physical contact (e.g., bare hands on chemical interfaces), missing structural components (e.g., no retort stands), and fundamentally wrong setups (e.g., unlit burners during an AAS measurement). Fixing these errors manually requires constant and repetitive prompting.

## The Solution: Protocol-First Strategy
Instead of starting with an image or guessing a prompt, this workflow treats the AI as an entity that must follow a Standard Operating Procedure (SOP). 

### ⚙️ Step 1: Protocol Extraction (The "Textbook" Phase)
Before writing any prompt or searching for images, research the exact Standard Operating Procedure (SOP) of the experiment. Extract the absolute, non-negotiable physical constraints.

*Example (Rotary Evaporator):*
- Condenser must be vertical.
- Evaporation flask must be diagonal and partially submerged in a warm water bath.
- Glass joints must be secured with a Keck clip.
- Operator's hand must be on the top vent valve to release pressure.

### 🖼️ Step 2: Multi-Reference Sourcing
Search for actual photographs (e.g., Wikipedia Commons) that demonstrate the experiment being performed correctly according to the extracted SOP. You will feed 1-3 of these images into the AI via Image-to-Image (i2i) or Image Prompt features to establish the base silhouette and geometric boundaries.

### 📝 Step 3: Prompt Synthesis (The "Strict Constraint" Method)
Inject the SOP physical constraints directly into the prompt using capitalized, geometric, and aggressive spatial rules. 

#### Prompt Template

```text
A photorealistic, highly detailed image of [CHARACTER DESCRIPTION, e.g., a 25-years-old Japanese woman, short black bob hair with bangs, wearing clear safety goggles, wearing a crisp white unbuttoned lab coat over a light blue collared shirt].

She is in a modern analytical science laboratory performing [NAME OF EXPERIMENT].

EXTREMELY STRICT RULES:
1. [CONSTRAINT 1: E.g., The tall glass burette is SECURELY HELD BY A METAL RETORT STAND AND CLAMP.]
2. [CONSTRAINT 2: E.g., Her RIGHT HAND is physically gripping the RED STOPCOCK VALVE attached halfway down the burette.]
3. [CONSTRAINT 3: E.g., Her EYES and FACE are looking DOWNWARD, sharply focused exactly on the pink liquid INSIDE the Erlenmeyer flask.]

No floating objects. Perfect anatomy. Real analytical science laboratory. Masterpiece, highly detailed.
```

### 🧠 Why this works
AI ignores nuance but responds strongly to:
1. **Capitalized keywords** (`SECURELY HELD`, `RIGHT HAND`, `DIAGONAL`).
2. **Explicit spatial relationships** (`INSIDE`, `IN FRONT OF`, `ATTACHED TO`).
3. **Over-specified mechanics** (`VERY THIN, HAIR-LIKE transparent CAPILLARY TUBE is SUBMERGED DEEP INSIDE`).

## Applying this Toolkit
By feeding this repository's methodologies to an AI agent, you can establish an automated loop: 
**User (rough prompt)** -> **Agent (SOP Search + Image Search + Strict Prompting)** -> **Accurate Generated Image**.
