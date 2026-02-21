# Linting Guidelines – Post-Generation Quality & Structure Checks

This file defines validation rules applied AFTER content is generated.
These rules do not ban specific phrases; they enforce structure, clarity,
and realism.

If a rule fails, the content should be revised before publishing.

--------------------------------------------------
1. STRUCTURE & FORMAT RULES
--------------------------------------------------

- Output must match runtime.output_format:
  - If output_format = "text" → NO HTML tags.
  - If output_format = "html" → Semantic HTML only (article, section, h1–h3, p, ul, li).

- Output must NOT include:
  - <!DOCTYPE>, <html>, <head>, <body>
  - Document-level <meta> or <title> tags.

- Each H2 section must contain:
  - At least one introductory paragraph.
  - Substantive content (not a single paragraph placeholder).

- No empty sections.
- No repeated sections with near-identical wording.

--------------------------------------------------
2. INTRO & FLOW CHECKS
--------------------------------------------------

- No meta-intros such as:
  - “In this article…”
  - “This guide will…”
  (Handled by forbidden phrases, but rechecked here.)

- First paragraph must:
  - Establish context or tension.
  - Avoid slogans or generic framing.
  - Avoid vague promises.

- Paragraph flow must be logical:
  - No abrupt topic jumps without a transition sentence.
  - Sections should progress problem → explanation → outcome.

--------------------------------------------------
3. CONTENT QUALITY CHECKS
--------------------------------------------------

- Vague claims must be anchored.
  Any sentence implying value, importance, or benefit must include:
  - a concrete example, OR
  - a specific scenario, OR
  - a measurable or observable outcome.

- Generic nouns must be clarified:
  - “this option”, “this method”, “this approach” must specify:
    - who it fits
    - when it applies
    - or what trade-off it introduces

- Authority claims must be grounded:
  - Phrases like “experts recommend”, “studies show”, “industry standard”
    require a concrete explanation or real-world context.
  - Otherwise, remove or rewrite.

--------------------------------------------------
4. INTENT & CONTENT-TYPE ALIGNMENT
--------------------------------------------------

- content_type = "page":
  - No long narrative storytelling at the top.
  - Focus on clarity, decisions, expectations.
  - CTAs may appear early and mid-content.

- content_type = "blog":
  - Softer intro and CTAs.
  - Educational tone unless intent requires otherwise.

- Intent alignment:
  - Informational → explain first, persuade lightly.
  - Commercial → compare, qualify, show fit.
  - Transactional → steps, readiness, next actions.
  - Navigational → clarity, confirmation, reassurance.

--------------------------------------------------
5. CTA & SALES PRESSURE CHECKS
--------------------------------------------------

- No pushy or urgency-driven CTAs.
- CTAs must:
  - Match intent strength.
  - Appear naturally within context.
  - Be phrased as options, not commands.

- Repeated CTAs must vary phrasing and purpose
  (e.g., decision CTA vs reassurance CTA).

--------------------------------------------------
6. SEO & REPETITION CHECKS
--------------------------------------------------

- Primary keyword:
  - Appears naturally in H1 and early body.
  - Not mechanically repeated in every section.

- Supporting keywords:
  - Distributed across sections.
  - No clustering or list stuffing.

- Sentence openers should vary.
  - Avoid repeated patterns like:
    “This…”, “It…”, “There are…”

--------------------------------------------------
7. FINAL SANITY CHECK
--------------------------------------------------

Before publishing, confirm:
- The content sounds like a knowledgeable human explaining a real situation.
- A subject-matter expert would not find it vague, hollow, or exaggerated.
- Nothing reads like it was written “to fill space”.

If any section feels generic, rewrite it with:
- a specific scenario
- a constraint
- or a real-world consequence.

--------------------------------------------------
8. PRICING ENFORCEMENT (HARD CHECK)
--------------------------------------------------

- If runtime.meta_fields does NOT provide pricing (or content-config does not explicitly provide pricing):
  - The content must NOT include:
    - currency symbols ($, £, €)
    - “starting at”, “from only”, “as low as”
    - specific numeric price claims
  - Allowed:
    - cost drivers, variables, ranges only if explicitly provided.

--------------------------------------------------
9. CTA COUNT ENFORCEMENT (HARD CHECK)
--------------------------------------------------

- If content_type = "blog":
  - Max 1 CTA total, near the end.
  - No CTA buttons/blocks in early or mid-body sections.

- If content_type = "page":
  - Multiple CTAs allowed, but:
    - No repeated identical CTA phrasing
    - No urgency/pushy phrasing (already covered in forbidden list)

--------------------------------------------------
10. FORBIDDEN PHRASES RECHECK (HARD CHECK)
--------------------------------------------------

- Re-scan for forbidden phrases and near-paraphrases.
- Re-scan for “soft academic hedging” used without a concrete scenario/range/example.
  (See forbidden-phrases.txt note.)
