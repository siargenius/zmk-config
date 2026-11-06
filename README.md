# Sweep keymap

The typing layout is QWERTY with symbol combos, home-row modifiers, and four
thumb keys. There is no symbol layer.

| Thumb | Tap | Hold |
| --- | --- | --- |
| Left outer | Tab | Shift |
| Left inner | Enter | Cmd on Mac, Ctrl on Windows |
| Right inner | Space | Space repeats |
| Right outer | Escape | Numbers and navigation |

Hold the left outer thumb, then press the right outer thumb for Backspace.
Hold the right outer thumb, then press the left outer thumb for Delete.
Both deletion keys repeat when held. The Backspace chord suppresses the Shift
from its thumb, while retaining other modifiers. Ordinary pinky Shift + Escape
still sends Shift + Escape. For modified deletion, hold the modifier before
entering the thumb chord.

Press both right thumbs together to toggle mouse mode. Release the thumbs to
move, scroll, or click; press the combo again or tap the Escape thumb to exit.
The existing media, Bluetooth, and Mac/Windows controls are on this same layer.
Exiting mouse mode preserves the current Mac/Windows mode.

## Symbol combos

The existing symbol combos remain, with these additions and relocations:

| Combo | Output |
| --- | --- |
| P + quote | Colon `:` |
| Quote + slash | Semicolon `;` |
| Period + slash | Backslash `\` |
| O + L | Plus `+` |
| L + period | Pipe `\|` |
| A + Z | Backtick (grave) |
| S + X | Tilde `~` |

Combos use a 50 ms window and are active on the typing and thumb-Shift layers.
They are disabled on the numbers/navigation and mouse layers.

## Modifier timing

Home-row modifiers use opposite-hand keys and all four thumbs as hold triggers.
This preserves same-hand Alt/Option + Tab and Ctrl + Tab. Modifier combinations
are evaluated on release so several modifiers can be held together.

The initial settings are balanced hold-taps with a 280 ms hold threshold,
150 ms prior-idle protection, and a 175 ms quick-tap window. A same-hand typing
sequence can still activate a modifier if it exceeds the hold threshold. During
fast typing, prior-idle protection favours letters; pause briefly before using
a home-row shortcut deliberately. Thumb hold-taps are separate, with a 200 ms
threshold and no prior-idle or quick-tap protection, so deliberate thumb holds
can follow typing or a preceding Tab/Enter/Escape tap.

## Trying the firmware

Build both `cradio_left` and `cradio_right` for `nice_nano_v2` using the existing
GitHub Actions workflow or a ZMK v0.3 build environment. Before daily use, check:

- Same-hand typing sequences that previously caused accidental shortcuts.
- Pinky Shift with the opposite hand, plus thumb Shift with either hand.
- Left-handed Alt/Option + Tab, Ctrl + Tab, and combined modifiers + Tab.
- Escape, repeating Backspace/Delete, and modified Backspace/Delete.
- Every new symbol combo, including the ones on home-row modifier positions.
- Mouse entry, exit by either method, diagonal movement, and dragging.
- Mouse entry/exit while using the Windows Bluetooth profile.

Build success verifies firmware compatibility; the timings need a typing trial
on the physical keyboard.
