# partner-ollama-gemma

Partner teks untuk drafting, rewrite, niche documentation, dan content prep yang tetap ringan.

## Tujuan

Repo ini adalah baseline partner khusus model **gemma** untuk ekosistem OpenClaw + n8n Ayang. Fokusnya bukan membuat sistem besar di dalam repo, tapi memberi arah yang stabil, ringan, dan mudah dipakai pada **Google Cloud Shell gratis**.

## Prinsip desain

- kecil, cepat, dan murah dijalankan
- minim dependency tambahan
- tidak menyimpan artefak besar di repo
- cocok untuk sesi Cloud Shell yang ephemeral
- output harus mudah dipakai ulang oleh n8n

## Peran utama

- model: `gemma`
- role: `editorial-research-partner`
- use in n8n: Drafting, rewriting, editorial cleanup, and structured content generation nodes.

## Cocok untuk

- rewrite and polish drafts
- summarize source material
- prepare outlines and niche docs
- turn notes into publish-ready structure
- generate response variants with consistent tone

## Hindari untuk

- precise code generation as primary task
- long-running autonomous loops
- large local indexing
- heavy multi-step stateful execution

## Struktur awal

- `configs/partner.profile.json` — profil runtime dan guardrails partner
- `docs/CLOUD_SHELL_PROFILE.md` — batas desain agar tetap stabil di Cloud Shell gratis
- `docs/N8N_ROLE.md` — peran partner di workflow n8n
- `prompts/SYSTEM.md` — prompt sistem dasar partner
- `tasks/BACKLOG.md` — backlog implementasi awal
- `scripts/preflight.sh` — cek ringan sebelum dipakai di Cloud Shell

## Quick start

```bash
bash scripts/preflight.sh
cat configs/partner.profile.json
cat prompts/SYSTEM.md
```

## Catatan

Repo ini sengaja dibuat **tipis**. Di Cloud Shell gratis, kestabilan lebih penting daripada banyak fitur. Simpan logika berat di n8n/OpenClaw atau service remote, bukan di repo partner ini.
