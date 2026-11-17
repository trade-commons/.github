# Contributing

## Before the code

The Global Trade Commons implements standards governed by others and authors none of them. A
contribution that changes what a specification means belongs upstream, not here. If implementation
work shows that a specification is wrong, silent or ambiguous, raise it with the body that governs it
through its change-request process, and record in the issue here which interpretation this code
adopted in the meantime. Resolving it locally produces a second standard, and the normative one then
becomes the less used.

Nothing in this organisation forks a specification. Schemas, contexts, vocabularies and registers are
referenced at their published location, never copied in.

## The Developer Certificate of Origin

Every commit must be signed off:

```
git commit -s -m "your message"
```

That appends `Signed-off-by: Your Name <your@email>` and certifies the
[Developer Certificate of Origin](https://developercertificate.org/): that you wrote the
contribution or have the right to submit it under the repository's licence.

Copyright stays with you. Inbound equals outbound, so your contribution is licensed to everyone on
the same terms the repository already uses, and no party, the foundation included, may relicense it.
There is no contributor licence agreement, and there will not be one: aggregating copyright in one
party is what would let a future host lock the commons, which the charter forbids.

## Licensing

Code is Apache-2.0, for the express patent grant and defensive termination. Do not introduce a
dependency whose licence is incompatible with that without raising it first.

A permissive licence says nothing about what the code depends on. UN/CEFACT specifications are openly
published; the WCO Data Model is made available to WCO members. A component that maps between them
depends on both and relicenses neither, so state in its README what a user must obtain and from whom
rather than vendoring the material or assuming they already hold it.

## Dependency direction

Three tiers, and one rule that keeps them apart.

- **Libraries** are imported by other things.
- **Services** are deployed and operated.
- **Applications** are used directly by a person.

**An application contains no protocol code.** No signing, no decentralised identifier resolution, no
schema fetching, no SHACL evaluation. An application that needs any of those calls a library or a
service. Where continuous integration checks this, a pull request that inverts the direction fails
rather than being caught in review.

This breaks when an application needs something a library does not yet expose and the author is
working to a deadline. The fix is to extend the library in the same pull request, not to inline it.

## Portability

No component may depend on infrastructure only the Commons can provide. Every service must be
deployable by a third party from its own repository, and a hosted instance must be one deployment of
a thing anyone can run. A configuration an operator cannot keep private is a defect, because some
operators run classified rules.

## Pull requests

Keep them small enough to review. Say what changes and why, and link the issue. Explain a decision
that is not obvious from the diff, since the reviewer who needs it may be reading in a year.

A new repository is not opened without a corresponding entry in the component catalogue naming who
maintains it. A component nobody is accountable for should not exist.
