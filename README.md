# Adaptive AI Custom Instructions

A compact custom-instruction pattern for general-purpose LLM use, designed to support **adaptive roles, evidence discipline, review convergence, delta-based change control, authority separation, scope restraint, and explicit stopping behavior**.

This repository does **not** claim a novel AI architecture, deterministic governance, or host-level enforcement. It is an instruction-layer pattern intended to improve interaction quality and reduce common failure modes such as role leakage, repetitive re-review, scope expansion, and authority conflation.

## Why this exists

General-purpose AI assistants are often given one permanent persona such as “strategic advisor,” “co-founder,” or “expert reviewer.” That can create role leakage: the assistant carries an analytical or adversarial posture into tasks that only need a tutor, writing partner, assistant, conversational companion, or specialist.

This pattern instead uses:

- **adaptive, task-scoped roles**;
- **explicit priority ordering** when instructions conflict;
- **evidence and uncertainty discipline**;
- **review convergence** instead of endless criticism loops;
- **delta-based revision** instead of full recomputation;
- **clear separation of discussion, recommendation, decision, approval, authorization, and execution**;
- **minimum necessary scope and capability**;
- an explicit **stop rule**.

## Repository contents

- [`CUSTOM_INSTRUCTIONS_TEMPLATE.md`](CUSTOM_INSTRUCTIONS_TEMPLATE.md) — generic reusable template.
- [`EXAMPLE_RACHMAT.md`](EXAMPLE_RACHMAT.md) — one concrete implementation for a founder/operator use case.
- [`LICENSE`](LICENSE) — MIT License.

## Design principles

### 1. Role is adaptive, not permanent

Use the minimum role required for the current objective. An assistant may be a strategist in one task, a tutor in another, and a writing partner in the next.

### 2. Explicit user intent wins

The current task objective and explicit role override default posture, while authority and evidence boundaries remain intact.

### 3. Review should converge

A previously reviewed or locked baseline should not be reopened without a material reason such as a delta, new evidence, failed test, contradiction, changed objective, changed material condition, or an explicit instruction to reopen it.

### 4. Revisions are delta-based

When a requested change is explicit, apply the delta and preserve unspecified parts.

### 5. Analytical quality does not create authority

Discussion, recommendation, decision, approval, authorization, and execution remain distinct states.

### 6. More process is not automatically better

Do not add specialists, tools, research, frameworks, or deeper reasoning unless they can materially improve the answer, reduce risk, or add evidence.

### 7. Stop when done

Further possible improvement is not, by itself, a reason to continue.

## How to use

1. Copy [`CUSTOM_INSTRUCTIONS_TEMPLATE.md`](CUSTOM_INSTRUCTIONS_TEMPLATE.md).
2. Replace bracketed placeholders such as `[PRIMARY_LANGUAGE]` and `[PRIMARY_JURISDICTION]`.
3. Remove lenses that are not relevant to your work.
4. Keep the instruction layer compact enough to remain reliably active.
5. Put project-specific rules, current state, files, and detailed methods in project instructions or knowledge sources rather than the global custom-instruction layer.

## Maturity and limitations

**Status:** Public instruction pattern / reusable baseline.

This repository specifies preferred assistant behavior. It does **not** provide:

- authentication or access control;
- deterministic policy enforcement;
- tool sandboxing;
- source isolation;
- execution gating;
- persistence guarantees;
- external validation;
- guaranteed factual correctness;
- guaranteed convergence.

Prompt-level instructions can influence behavior but are not equivalent to runtime or infrastructure controls.

## Attribution

Original pattern by **Rachmat Efendi**.

## License

MIT License. See [`LICENSE`](LICENSE).
