# Contributing

The wire family is one project spread across several repositories — [swift-wire], [wire-mvc],
[wire-open-api], [wire-configuration], [wire-mvc-examples], [wire-mvc-hummingbird] and
[wire-mvc-performance]. This document governs all of them, and GitHub serves it for any repository
that does not carry its own.

Some repositories do carry their own `CONTRIBUTING.md`. Those cover building and testing that
particular package, which is repository-specific and often surprising. They add to this document
rather than replacing it.

> The project is experimental, and public API changes without warning. That is what the proposals
> process below exists for — not a reason to skip it.

## What needs a proposal

The gate is **what a change does to intended behaviour**. It is not about the size of the diff, and
it is not about what tools you used to write it.

**Open a pull request directly for:**

- **A bug fix** — restoring behaviour or a design that was already intended. The test is whether you
  can point at the intent the code fails to meet: a doc comment, a design note, a test, a proposal.
  If you cannot point at one, what you have is a behaviour change, however obviously better it is.
- Documentation, tests, CI and build tooling.
- Performance work that changes no observable behaviour.

**Write a proposal first for:**

- A change in behaviour, including one you consider an improvement.
- A new feature, or public API added, removed or renamed.
- A large-scale refactor — one that crosses module or repository boundaries, or changes a pattern
  the codebase applies in many places.
- A new dependency.

If a change sits on the line, open an issue and ask before writing the code. Being told "just send
the pull request" costs you an afternoon. Having a finished feature declined because its design was
never agreed costs you a great deal more, and it is a bad experience this process exists to prevent.

## Using AI

AI assistance is welcome anywhere in this project, proposals included. There is nothing to disclose,
no marker to add to a file, and no trailer to add to a commit message.

The project asks three things instead, none of which are about tools:

**You are the author of what you submit.** You must have read and understood every line, be able to
explain why it is correct, and have the right to contribute it under Apache-2.0 — which is the
representation section 5 of the licence takes your contribution under. Output that nobody has
reviewed is not a contribution.

**The design judgement has to be a person's.** A model may draft a proposal's prose. It cannot
supply the decision the proposal exists to record. Read the notes under `Documentation/Notes/` and
the files already in `Proposals/`: their value is not that they describe a design, it is that they
say *why* the design is what it is, so that the reasoning is not re-derived — or quietly reversed —
a year later. Reasoning that nobody has checked cannot do that job.

**A pull request is not where you find out whether it works.** Run the tests and the repository's
own gates before opening one.

None of this is a rule about detecting AI use, which cannot be done and would be the wrong thing to
police. It is a rule about what counts as a contribution, and it was true before any of it was
written down.

## The proposals process

Proposals live in `Proposals/` in the repository the change lands in, and follow the shape the
existing ones already set.

**1. Open an issue in the repository the change lands in.** Describe the gap rather than the
solution — what does not work, or what cannot currently be expressed. If a change spans
repositories, the issue belongs to the one whose code changes; where that is genuinely more than
one, use the repository furthest down the dependency graph and have the proposal say why it lands
there.

**2. Wait for agreement in principle.** A careful proposal for something the project does not want
is wasted work, and that is a cheap conversation to have first.

**3. Write the proposal as `Proposals/<Name>.md`.** It opens with a status blockquote naming the
tracking issue:

```markdown
> **Status:** not implemented; tracked as
> [swift-wire/wire-mvc#187](https://github.com/swift-wire/wire-mvc/issues/187), which owns the
> status. Extends [WireMVCDesign.md](../Documentation/Notes/WireMVCDesign.md). Lands in `wire-mvc`.
```

**The issue owns the status, not the file.** A document that records its own progress goes stale
silently and nobody notices; an issue is the durable reference, and it is where the state lives.

**4. Land the proposal as its own pull request**, separate from any implementation. It is reviewed
as a design. Merging it means the design is agreed, not that the work is done.

**5. The implementation references the proposal** and updates the tracking issue as it lands. A
proposal that has shipped says so in its status blockquote and stays where it is — the record of why
is worth more after the fact than during.

### What a proposal contains

There is no template to fill in, and the proposals already in the repositories are the best guide.
What they have in common:

- **The problem, stated as something concrete that does not work.** Usually two or three observations
  that look inconsistent with one another.
- **The principle that resolves it** — the rule the specific answers follow from, rather than a list
  of the answers.
- **What follows from that rule**, including the consequences you did not initially like.
- **What was considered and rejected, and why.** This is the part that stops the question being
  reopened every six months.
- **What is deliberately deferred**, and what would force it to be picked up.

Length is whatever the argument needs; several of the existing ones are long. A proposal that is
mostly rationale and lightly API is the right shape. The reverse usually means the design is not
settled yet.

## Pull requests

Explain **why**, not what — the diff already says what. Commit messages here are prose, and the
history is meant to read as an account of how the design arrived where it did.

Do not add tool attribution trailers: no `Co-Authored-By:` for a model, no generation notices, no
session links. See *Using AI* above — what matters is that you stand behind the change, and a
trailer does not establish that.

Every repository's gates must pass, including `Scripts/check-license-headers.sh`. A new Swift file
needs the two-line licence header; the script prints the exact lines if you forget.

## Licence

Apache-2.0. Contributions are licensed inbound on the same terms as outbound, under section 5 of the
licence, so there is no CLA to sign and no separate agreement to accept.

[swift-wire]: https://github.com/swift-wire/swift-wire
[wire-mvc]: https://github.com/swift-wire/wire-mvc
[wire-open-api]: https://github.com/swift-wire/wire-open-api
[wire-configuration]: https://github.com/swift-wire/wire-configuration
[wire-mvc-examples]: https://github.com/swift-wire/wire-mvc-examples
[wire-mvc-hummingbird]: https://github.com/swift-wire/wire-mvc-hummingbird
[wire-mvc-performance]: https://github.com/swift-wire/wire-mvc-performance
