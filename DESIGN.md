# Design System Document: The Alchemist’s Codex

## 1. Overview & Creative North Star: "The Arcane Scholar"
This design system is not a mere interface; it is a digital grimoire. Our Creative North Star is **"The Arcane Scholar."** We move away from the sterile, flat "SaaS" look and toward a tactile, editorial experience that feels like discovering an ancient laboratory at midnight.

To achieve this, we break the rigid digital grid with **intentional asymmetry**. Elements should feel "placed" rather than "slotted," using overlapping layers and deep tonal shifts to create a sense of physical space. We prioritize atmosphere over efficiency, using high-contrast typography scales and glowing focal points to guide the eye through the "mist."

## 2. Colors: Luminance & Shadow
Our palette is rooted in the darkness of an ancient lab, punctuated by the "chemical reactions" of emerald and amber.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders to define sections. We define space through "The Fog"—subtle shifts in background tokens. For example, a `surface-container-low` module should sit atop a `surface` background to define its boundary. 

### Surface Hierarchy & Nesting
Treat the UI as a series of nested vessels. 
- **The Laboratory Floor (`surface` / `#16121b`):** The base level of the application.
- **The Oak Workbench (`surface-container-low` / `#1e1a23`):** Used for large secondary content areas.
- **The Glass Flasks (`surface-container-highest` / `#38333d`):** Used for active, interactive cards or modals.
- **The Glow:** Use `primary` (`#dcb8ff`) and `secondary` (`#66dd8b`) with 20-40px blurs to create "light leaks" behind key components, simulating the glow of magical reagents.

### The "Glass & Gradient" Rule
To capture the "Alchemy" aesthetic, interactive elements should utilize **Glassmorphism**. Apply `surface-variant` at 60% opacity with a `24px` backdrop blur. 
- **Signature Gradient:** For primary actions, use a linear gradient from `primary` (`#dcb8ff`) to `primary-container` (`#4a0084`) at a 135-degree angle. This provides a "soul" that flat color cannot replicate.

## 3. Typography: The Script of Ages
We pair a high-character Serif with a functional Sans-Serif to balance mysticism with legibility.

*   **Display & Headlines (Newsreader):** This is our "Incantation" font. Use `display-lg` (3.5rem) for hero moments. The tight tracking and elegant serifs should feel like a hand-pressed manuscript.
*   **Labels & UI (Manrope):** This is our "Measurement" font. Used for data, labels, and small instructions. It provides a clean, modern contrast that ensures the "lab results" are readable.
*   **Hierarchy Note:** Always lead with a large Serif headline to set the tone, followed by Manrope for functional metadata. Never use the Serif for labels or buttons; it must remain "precious."

## 4. Elevation & Depth: Tonal Layering
Traditional shadows are too "digital." In this system, depth is achieved through **Ambient Light.**

*   **The Layering Principle:** Stack `surface-container-lowest` on `surface-container-low` to create an "inset" look, as if carved into wood. 
*   **Ambient Shadows:** For floating elements (modals/popovers), use a shadow with a `32px` blur, `0px` offset, and `8%` opacity. The shadow color must be a tint of `primary_container` (`#4a0084`) rather than black, creating a "purple-dark" glow.
*   **The "Ghost Border" Fallback:** If accessibility requires a stroke, use `outline-variant` (`#4c4451`) at **15% opacity**. It should be felt, not seen.
*   **Glassmorphism:** Use semi-transparent layers for any element that represents a "potion" or "reagent." This allows the "embers" of the background to bleed through, softening the interface.

## 5. Components: Crafted Artifacts

### Buttons (The Philosopher’s Stone)
*   **Primary:** A gradient from `primary` to `primary-container`. `0.5rem` (lg) corner radius. Add a subtle `1px` inner glow (top-down) using `primary_fixed`.
*   **Secondary:** Ghost style. Transparent background with a `1px` border of `secondary` at 20% opacity. Text color is `secondary`.
*   **Tertiary:** Pure text using `tertiary` (`#fbbc00`) with a "glow" hover state.

### Input Fields (The Ledger)
*   No boxes. Use a bottom-only border of `outline-variant` at 30%. On focus, the border transitions to a `secondary` (`#66dd8b`) glow with a subtle backdrop-blur inside the input area.

### Cards & Lists (The Ingredient Rack)
*   **Forbid Dividers:** Use `1.4rem` (4) spacing or a shift from `surface-container-low` to `surface-container-highest` to separate list items. 
*   **Visual Texture:** Cards should feature a 5% opacity "grain" overlay to mimic ancient vellum or aged wood.

### Additional Artifacts
*   **Reagent Chips:** Small capsules with `secondary_container` backgrounds and `on_secondary_container` text. Use these for status effects or ingredients.
*   **The "Ember" Tooltip:** `surface_bright` background with an `amber` (`tertiary`) arrow, used for "secret hints" or lore details.

## 6. Do's and Don'ts

### Do:
*   **Embrace Asymmetry:** Let images or decorative elements overlap container edges.
*   **Use Tonal Shifts:** Define sections by changing the background from `surface` to `surface_container_low`.
*   **Prioritize the Serif:** Let the `Newsreader` font do the heavy lifting for the brand's personality.

### Don't:
*   **No "Safety Blue":** Never use standard hex blues. If you need a "functional" color, use Emerald (`secondary`) for success and Amber (`tertiary`) for warnings.
*   **No Opaque Borders:** Never use a solid, high-contrast line to separate content. It kills the "mystical" atmosphere.
*   **No Perfect Grids:** Avoid the "Bootstrap" look. Vary your column widths to create an editorial, magazine-like flow.
*   **No Pure Black:** Our darkest color is `#100d15` (`surface_container_lowest`). Pure black (`#000000`) is too harsh for this alchemical world.