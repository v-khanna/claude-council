# Claude Council

A Claude Code skill that provides multi-perspective analysis on any problem. Dispatches 5 persona agents in parallel, runs a debate round, then synthesizes into a final recommendation. Claude-only — no external API keys needed.

## How It Works

1. **Round 1**: 5 agents with distinct personas (Pragmatist, Critic, Architect, User Advocate, Contrarian) analyze your problem in parallel
2. **Round 2**: 2 debate agents read all Round 1 analyses and argue the strongest disagreements
3. **Round 3**: 1 synthesizer produces a final recommendation with consensus, disagreements, risks, and confidence level

## Install

Copy the skill to your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/council
cp SKILL.md ~/.claude/skills/council/SKILL.md
```

## Usage

In Claude Code:

```
/council Should we build this feature in-house or use a third-party API?
```

```
/council We're thinking about raising prices 20% — what are we missing?
```

```
/council Should we launch with a smaller feature set now or wait until it's complete?
```

Works on any decision — product, strategy, architecture, hiring, pricing, whatever.

### Quick Mode

Skip the debate round for faster results:

```
/council --quick Is this partnership worth pursuing?
```

## The 5 Personas

| Persona | Lens | Role |
|---------|------|------|
| **Pragmatist** | "What's the simplest thing that works?" | Shipping, trade-offs, avoiding over-engineering |
| **Critic** | "What could go wrong?" | Flaws, edge cases, risks, security |
| **Architect** | "How does this fit the bigger picture?" | Scalability, maintainability, long-term consequences |
| **User Advocate** | "What does the end user experience?" | UX, clarity, accessibility, real-world impact |
| **Contrarian** | "What if the opposite is true?" | Challenge assumptions, prevent groupthink |

## The 5 Universal Questions

Each persona answers:

1. What is the core problem being solved, and is it the right problem?
2. What are the trade-offs of the proposed approach?
3. What's the biggest risk or blindspot?
4. What would you change or do differently?
5. What's your confidence level (1-10) and what would change it?

## Output

The final synthesis includes:
- **Consensus** — what all personas agreed on
- **Key Disagreements** — where they diverged and why
- **Recommendation** — actionable next steps
- **Risk Register** — top risks ranked by severity
- **Confidence** — overall assessment with caveats

## License

MIT
