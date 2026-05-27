# Divine OS - Orchestrateur IA Autonome

Atelier de missions IA local. Soumettez un objectif, Divine OS orchestre un cycle architect / builder / reviewer entierement piloté par Claude. Les artifacts de chaque cycle sont persistes sur disque.

## Concept

Divine OS analyse le codebase cible, derive une taxonomie de taches, enrichit les prompts avec le contrat runtime du projet, puis execute des cycles IA autonomes jusqu a completion.

bash
Objectif -> Architect (plan) -> Builder (code) -> Reviewer (validation) -> Artifact


## Stack

- Python 3.11+
- Claude API (Anthropic) - modeles Sonnet / Opus
- FastAPI (dashboard web local)
- SQLite (persistance des missions et cycles)
- Click (CLI)
- Watchdog (surveillance fichiers)

## Fonctionnalites

- Analyse statique du codebase cible (embedded source tree)
- Derivation automatique : taxonomie de taches, modes coordinateur, marqueurs outils
- Enrichissement dynamique des prompts architect / builder / reviewer
- Cycles IA avec artifacts ecrits sur disque
- Dashboard web local (http://127.0.0.1:8787)
- CLI : init, dashboard, claude-brain, run-mission
- Rapport d analyse du modele Claude embarque

## Demarrage

bash
py -m pip install -e .
py -m divine_os init
py -m divine_os dashboard


Variable requise : ANTHROPIC_API_KEY