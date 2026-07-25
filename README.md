# Claude Output Cleaner

A single-file HTML tool that cleans up text copied from Claude Code's terminal output so it pastes cleanly into documents, messages, and editors.

## The problem

When you copy text from Claude Code, the clipboard gets:

- **Leading spaces** on every line from terminal padding
- **Hard line breaks** where the terminal wrapped — pasting into a document gives you ragged, one-line-per-row paragraphs instead of flowing text
- **A `⏺` bullet** at the start of each response block
- **`▎` quote markers** instead of standard markdown `>` blockquotes

Fixing this by hand means opening vi and running `:%s/  //` then `J`-ing lines together. This tool does it in one paste.

## Usage

Open `claude-text-cleaner.html` in a browser and bookmark it. Paste Claude Code output into the left panel, copy the cleaned result from the right.

Three toggles control what gets cleaned:

- **Strip leading spaces** — removes all leading whitespace from each line
- **Join wrapped lines** — merges hard-wrapped paragraph lines back into flowing text
- **Preserve code blocks** — keeps fenced code blocks (` ``` `) intact

The cleaner also:

- Converts `▎`-quoted blocks into markdown `> ` blockquotes with joined lines
- Preserves markdown structure (headings, lists, blockquotes, horizontal rules)
- Strips the `⏺` bullet marker from response starts

## No dependencies

One HTML file, no build step, no external resources. Works offline. Respects your OS light/dark theme.
