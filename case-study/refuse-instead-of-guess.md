# Why my quote agent refuses to guess

*Samir Mammadli · Notes from building the [Service-Business Quote Agent](../README.md)*

Most AI demos are judged by whether they always produce an answer. When I designed a quoting tool for a small HVAC contractor, I went the other way. The most important thing it does is **say no**.

## A price is a promise

A quote isn't a draft email. Once a customer sees a number, the business has to stand behind it. If it's too high, they lose the job. If it's too low, they lose margin. Either way, the owner needs to explain where the number came from.

That ruled out letting AI generate prices. A language model can produce a plausible number every time, and that's exactly the problem: plausible isn't the same as defensible.

## Learn from the business's own history

Prices come from the contractor's own past quotes instead. The engine fits labour rate, category markup, repeat-customer discount and seasonal effects from validated history, so every price traces back to jobs the business has actually done.

## Six reasons to say no

Before returning a price, the engine runs six checks. Is this a known category? Does it have an accepted pricing rule? Is the job within the historical range? Are there enough comparable jobs? Is pricing in this category consistent? Is every discount or surcharge rule it needs accepted?

If any check fails, there's no price. The owner sees which checks failed, which also tells them what data to collect next.

## Where AI does belong

AI still has a job: polishing the wording of a quote. That's low-risk, and a person approves it anyway. Even there, the assistant sees only the service category, equipment and job description. It never gets the customer's name, contact details or the price.

## What I took from it

- **Knowing when not to answer is a feature.** A tool that refuses when its data is weak earns more trust than one that always answers.
- **Adoption depends on data more than on the interface.** The import-and-validate step matters as much as the quote screen.
- **Put AI where mistakes are cheap.** Drawing that line early kept the design simple and the output defensible.

The product is a pilot candidate. It runs as a local demo on synthetic data, and no customer results are claimed yet. The next step is a pilot with one contractor, comparing the engine's prices against the quotes they actually sent.

---

<sub>© 2026 Samir Mammadli. All rights reserved.</sub>
