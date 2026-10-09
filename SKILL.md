---
name: cyberpunk-2077-transfer
slug: cyberpunk-2077-transfer
displayName: 赛博朋克实况转绘
version: 1.0.0
summary: "把实拍照片一键转成《赛博朋克2077》游戏截图风格：霓虹夜城、雨夜反射、义体边缘行者、中文霓虹招牌与扫描模式 UI，附可复用的转绘提示词模板。"
license: MIT
icon: icon.png
description: "Transform real-world reference photos into Cyberpunk 2077 in-game screenshot prompts or generated images with maximum CP2077 rendering fidelity. Use when the user provides night city, neon street, night market, bar, night portrait, rainy street, or urban night photos and asks for Cyberpunk 2077 screenshot transfer, photo-to-night-city prompt writing, image-to-image prompts, cyberware and neon signage, or reusable real-photo-to-CP2077 workflows."
---

# 赛博朋克实况转绘

Convert real-world reference photos into **Cyberpunk 2077 gameplay screenshots**. The priority is **MAXIMUM CP2077 IN-GAME RENDERING FIDELITY**: neon-drenched Night City, rain-slicked streets, chrome and holograms — dense, vertical, electric urban night.

This is a fan-made, non-commercial workflow for personal learning, research, and prompt testing only. It is not affiliated with, endorsed by, sponsored by, or approved by CD PROJEKT RED, Cyberpunk 2077, or any related rights holders. Do not use outputs for commercial sale, advertising, merchandising, paid services, or uses that imply official authorization.

## Output Mode

- If the user asks for prompts, return the final prompt in one code block unless they ask for explanation.
- If the user asks to generate images, use the available image generation workflow.
- If generating from a reference photo, generate first, then provide the final prompt unless the user asks for image only.
- If both prompt and image are requested, generate first, then provide the prompt.
- Use Chinese for user-facing final prompts, but keep the English rendering-control blocks exactly because they strongly steer image models.

## Reference Analysis

Before writing the prompt, identify only what affects transfer:

- Core subject: night street, skyline, night market, bar, club, alley, overpass, night portrait.
- Recognizable features to preserve: skyline silhouette, street layout, landmark shape, crowd composition, water reflection.
- Night City mapping: map the real scene to Night City districts — downtown → 市中心, market street → 歌舞伎区, riverfront → 海伍德滨水, alley → 太平州小巷.
- Scene type: street stroll, night market, bar meet, rain walk, rooftop overlook.
- Environment: rain or dry, neon density, crowd level.
- UI needs: scanner overlay, or no UI.
- Daytime scenes: convert to night — Night City lives at night.

Preserve the reference photo's identity. Electrify it into a Night City moment, not a neon poster.

## Planning Workflow

Before filling the final prompt, decide:

1. 场景类型与夜之城映射：街头 / 夜市 / 酒吧 / 雨夜 / 天台，对应哪个区域气质
2. 环境设定：雨夜或干夜、霓虹密度、人群
3. 角色模式：默认将照片人物转译为夜之城边缘行者（义体、霓虹纹身、街头穿搭，材质对标 CP2077）；或无角色纯街景
4. 赛博元素：霓虹中文招牌 / 全息广告 / 飞行载具 / 义体诊所灯箱，按场景点缀
5. UI 需求：扫描模式覆盖层 / 无 UI
6. 构图：远景 / 中景 / 近景，保持第一人称沉浸感或电影感

Do not output this planning checklist unless the user asks. Reflect the decisions in the final prompt.

## Prompt Template

When a reference image is provided, always derive concrete content from the image. Never output placeholders.

Use this order for prompt-only output and image-generation prompts:

```text
Cyberpunk 2077 gameplay screenshot - MAXIMUM CP2077 IN-GAME RENDERING FIDELITY.
This must look EXACTLY like actual Cyberpunk 2077 gameplay footage, NOT generic sci-fi, NOT anime, NOT a neon poster.

RENDERING STYLE - CP2077 IN-GAME (CRITICAL):
Dense neon-drenched urban night; detailed game-engine 3D with realistic materials; WET RAIN-SLICKED surfaces with neon reflections; vertical layered cityscape; holographic ads and glowing signage everywhere; chrome, leather, and wet asphalt; cinematic but GAME-DIEGETIC, not a movie still; NO flat illustration, NO cartoon shading.

SCENE：保留<参考图核心构图、主体、地标、天际线等识别特征>，统一转译为夜晚，映射为<夜之城区域气质>；白天场景一律转夜景；画面尺寸比例：9:16，1440x2560
CHARACTER：<默认：照片人物转译为夜之城边缘行者，义体细节、霓虹纹身、街头穿搭，材质对标 CP2077>；<一句话写清动作与神态>
CYBERPUNK ELEMENTS：<3-7 个场景适配元素，只列名称，如：中文霓虹招牌、全息广告、飞行载具、义体诊所、雨夜积水>
UI：<按需加入扫描模式覆盖层：人物/载具描边高亮 + 中文标签；或无 UI>；场景内真实招牌转为中文霓虹招牌配 2-4 字中文

LIGHTING - CP2077 GAME ENGINE STYLE:
Neon-dominated night lighting: magenta, cyan, amber, red washing over wet streets; strong colored reflections on every wet surface; deep shadows between neon pools; rain glow where raining; Overall DARK but ELECTRIC, never flat daylight.

COLOR PALETTE - CP2077 <场景类型>:
Neon: hot magenta, electric cyan, amber, warning red — dense and layered
Street: wet asphalt blacks with neon reflections
Sky: deep night blue-purple with haze glow

MATERIALS - CP2077 GAME SURFACES:
Wet asphalt: mirror-like neon reflections; Chrome: sharp bright highlights; Skin: realistic with subtle cyberware seams; Clothing: leather, techwear textures.

ATMOSPHERE - NIGHT CITY:
Rain or humid haze; volumetric neon glow; distant flying vehicle lights; layered depth from foreground rain to background towers.

STRICT SELF-CHECK TARGET:
The final image must pass: dense neon-drenched Night City night; wet reflective surfaces everywhere; characters read as CP2077 edgerunners, not modern photo people; Chinese neon signage is game-diegetic; UI, if any, is scanner-mode game state, never a poster title; reference composition and landmark relations preserved; no daylight, no flat illustration, no generic sci-fi emptiness.

FINAL EMPHASIS - MUST LOOK LIKE ACTUAL CP2077 GAMEPLAY:
Dense neon night. Wet reflective streets. Electric vertical city. NOT generic sci-fi, NOT anime, NOT a neon poster.
```

## Required Prompt Fields

Every final prompt must include:

- Scene description: concrete character, action, environment, composition, preserved reference features, and Night City mapping. All scenes convert to night.
- Character mode: default Night City edgerunner, or no character.
- `COLOR PALETTE`: neon magenta/cyan/amber/red over wet dark streets.
- `MATERIALS`: wet asphalt, chrome, techwear.
- `ATMOSPHERE`: rain/haze, volumetric neon, flying vehicles.
- `STRICT SELF-CHECK TARGET`: a compact pass/fail target that names neon density, wet reflections, edgerunner characters, and reference preservation.
- Opening and final emphasis blocks, unchanged in meaning.

## Style Anchor Rules

Start every image prompt with these two lines:

```text
Cyberpunk 2077 gameplay screenshot - MAXIMUM CP2077 IN-GAME RENDERING FIDELITY.
This must look EXACTLY like actual Cyberpunk 2077 gameplay footage, NOT generic sci-fi, NOT anime, NOT a neon poster.
```

Then include `RENDERING STYLE - CP2077 IN-GAME (CRITICAL)` before scene content. Include `STRICT SELF-CHECK TARGET` before final emphasis. End every prompt with `FINAL EMPHASIS - MUST LOOK LIKE ACTUAL CP2077 GAMEPLAY`.

Do not scatter extra style essays across the prompt. Rendering control lives in the opening, lighting, color, materials, atmosphere, and final emphasis blocks.

## CP2077 Rendering Calibration

Default to Cyberpunk 2077 gameplay:

- Always night; neon is the primary light source.
- Wet streets with mirror-like neon reflections are near-mandatory.
- Vertical density: signs, balconies, wires, holograms stacked overhead.
- Characters: cyberware (chrome limbs, optical implants, glowing tattoos), streetwear with techwear details.
- Signage: Chinese neon signs 2-4 characters, game-diegetic.
- Vehicles: flying cars with light trails in the sky, parked futuristic cars on streets.
- Scanner UI: edge-highlight outlines with small Chinese data labels, subtle and diegetic.
