# cli-wordle

A full-screen terminal Wordle clone in a single Python file. Plays the daily NYT puzzle, archive puzzles by number, or an offline zen mode with a curated common-word pool.

## Features

- Full-screen TUI with responsive layout — small, big, and huge-keyboard tiers based on terminal size.
- Live in-tile typing (no separate input field) with raw-mode keystroke handling.
- Daily puzzle pulled from the official NYT Wordle API, with stats and share text.
- Archive mode: replay any past puzzle by number (e.g. `-a 546`).
- Zen mode: unlimited offline rounds with a curated pool of ~2,800 common 5-letter words (mixed singulars + popular plurals).
- Hard mode with specific violation messages (not just "not in word list").
- Combined flags: `--hard --zen`, `--hard -a 546`.
- Press `C` after a daily/archive round to copy the share text to the clipboard.
- Ctrl-C, Ctrl-Z, or Esc to exit cleanly from any screen.

## Install

```bash
git clone https://github.com/<you>/cli-wordle.git
cd cli-wordle
chmod +x wordle
./wordle
```

Requires Python 3.8+.

## Usage

```
./wordle              # today's NYT puzzle
./wordle --hard       # today's puzzle in hard mode
./wordle --zen        # offline zen mode
./wordle --zen --hard # zen + hard
./wordle -a 546       # archive puzzle #546
./wordle -a 546 --hard
./wordle --help
```

## Word lists

- **Solutions** in zen mode are drawn from a curated ~2,800-word pool of common English 5-letter words.
- **Guesses** are validated against the canonical Wordle valid-guesses list (~14,800 words), fetched once on first run and cached at `~/.cache/wordle-cli/valid_guesses.txt`. Falls back to the system dictionary with synthesized inflections if offline.

## License

MIT.
