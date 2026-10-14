# PebbleMapper model list

`list.json` is the list of detection models [PebbleMapper](https://github.com/soloyant/PebbleMapper)
offers on its **Models** tab, for installation in one click. PebbleMapper reads it from this
repository's `main` branch and installs only what it names: each model's release, the exact
files of its software environment, and its weights, each with its size and SHA-256.

The list is maintained by the PebbleMapper maintainer. Every plug-in release it names is an
immutable GitHub release of the plug-in's own repository; weights come from addresses whose
content cannot change.

| File | What it is |
|---|---|
| `list.json` | the list (format 1) |
| `list.schema.json` | the JSON Schema of format 1 |

**Rules PebbleMapper enforces when it reads the list**: the whole list is refused if any entry
breaks the format; a list whose `list_version` is lower than one already accepted is refused;
files are fetched over HTTPS from a fixed set of hosts only; text from the list is shown as
plain text.

To add or update a model, the maintainer builds its release with
`tools/make_plugin_release.py` in the PebbleMapper repository, publishes it, adds the
generated entry here and increases `list_version`.

## Models currently listed

| Model | Plug-in | Licences |
|---|---|---|
| OrthoSAM (Chan, Rheinwalt & Bookhagen, 2026), releases 1.0.0 and 1.0.1 | [pebblemapper-backend-orthosam](https://github.com/soloyant/pebblemapper-backend-orthosam) | Apache-2.0 (OrthoSAM, Segment Anything), MIT (adapter) |
| Segmenteverygrain (Sylvester et al., 2025), release 1.0.0 | [pebblemapper-backend-segmenteverygrain](https://github.com/soloyant/pebblemapper-backend-segmenteverygrain) | Apache-2.0 (segmenteverygrain, SAM 2), MIT (adapter) |
| PebbleCountsAuto (Purinton & Bookhagen, 2019), release 1.0.0 | [pebblemapper-backend-pebblecounts](https://github.com/soloyant/pebblemapper-backend-pebblecounts) | GPL-3.0-or-later |

## Licence

The list itself is released under CC0 1.0. Each model keeps its own licence, given in its entry.
