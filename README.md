# Apple Punjabi Transliteration with Dvorak keys

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This is intentionally **not another Punjabi IME**. It is a conditional physical
key remap in front of Apple's built-in Punjabi Transliteration input source:

```text
ANSI physical key → Dvorak Roman character → Apple Punjabi Transliteration
```

Apple therefore continues to provide the Gurmukhi composition, candidate list,
language model, and learned suggestions. The remap is active only for Punjabi
Transliteration; every other input source is untouched.

## Install

1. In **System Settings → Keyboard → Text Input → Edit → +**, add
   **Punjabi → Transliteration**.
2. Copy `punjabi-transliteration-dvorak.json` to:
   `~/.config/karabiner/assets/complex_modifications/`
3. Open **Karabiner-Elements → Complex Modifications → Add predefined rule**.
4. Enable **Use ANSI Dvorak physical keys with Apple's Punjabi
   Transliteration**.
5. Select Punjabi Transliteration from the macOS input menu and type normally
   on Dvorak.

After this repository is public, the rule can also be imported directly using:

```text
karabiner://karabiner/assets/complex_modifications/import?url=https://raw.githubusercontent.com/zoravur/punjabi-transliteration-dvorak/main/punjabi-transliteration-dvorak.json
```

Do not paste the complete distributable JSON into Karabiner's **Add your own
rule** editor. That editor expects only the inner object containing
`description` and `manipulators`, while the distributable file is an asset
wrapper containing `title` and `rules`. If using the editor, paste the contents
of `punjabi-transliteration-dvorak-rule.json` instead.

The rule preserves modifiers, so Dvorak-position shortcuts continue to behave
as expected while the Punjabi input source is selected.

## Compatibility

- macOS 26.5 or newer (the Apple Punjabi Transliteration input source is the
  limiting dependency)
- Karabiner-Elements 11.2 or newer
- ANSI keyboard geometry

The rule recognizes Punjabi either as the input mode ID or input source ID
`com.apple.inputmethod.TransliterationIM.pa`. On a different macOS release, use
Karabiner-EventViewer's **Variables → input_source** panel to confirm the ID and
adjust the two regular expressions if Apple changes it.
