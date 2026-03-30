# The Jump Theorem — Prime Checker

**Part of *The Lift Survival Function* · W. Getachew · 2026 · math.NT**

🔗 **[Live demo → wessengetachew.github.io/Jump/](https://wessengetachew.github.io/Jump/)**

---

## Overview

This repository hosts an interactive exposition of the **Jump Theorem**, a result from the theory of the Lift Survival Function C(x). The core claim:

> *D(x) = d/dx log C(x) is smooth almost everywhere, but at exactly the integer primes — and only the primes — it has a sharp, isolated, invertible jump discontinuity.*

Composites pass in silence. Every prime announces itself with a calculable tremor.

---

## The Mathematics

### The Lift Survival Function C(x)

C(x) is an Euler product that records the long-run fraction of coprime residues surviving the lift from modular ring M to ring M+1:

$$C(x) = \prod_{p \leq x+1} \frac{p}{p+1} \cdot \prod_{p > x+1} \frac{p^2 - x - 1}{p^2 - 1}$$

As x → ∞, C(x) converges to the constant C ≈ 0.530711806246…

### The Jump Theorem

Define the log-derivative:

$$D(x) = \frac{d}{dx} \log C(x) = -\sum_{p \,>\, x+1} \frac{1}{p^2 - x - 1}$$

**Theorem.** D(x) is smooth on every open interval (p−1, q−1) between consecutive primes p, q. At x = p−1 for any prime p, D(x) has a jump discontinuity of exact size:

$$\Delta D\big|_{x=p-1} = \frac{1}{p(p-1)}$$

For every composite m, D(x) is continuous at x = m−1. No jump.

### Prime Recovery (Algebraic Inversion)

Given a jump of size s, recover the prime exactly via the quadratic formula:

$$p = \frac{1 + \sqrt{1 + 4/s}}{2}$$

For every prime p, the discriminant 1 + 4p(p−1) = (2p−1)² — always a perfect square. The formula returns an integer with no rounding.

### The φ Boundary

At s = 1, the discriminant is 5 — not a perfect square — and the formula returns φ = (1+√5)/2. This is the **supremum of the jump spectrum**: every prime jump satisfies s < 1, and s = 1 is approached but never attained. The phantom jump would occur at x = φ−1 ≈ 0.618, before the first real prime enters the sum.

---

## Four Constants

The framework generates four numerical constants:

| Constant | Value | Description |
|----------|-------|-------------|
| C ≈ 0.530711806246 | Lift Survival Rate | Long-run coprime fraction; equals F(2) |
| J ≈ 0.773154968933 | Total Jump Content | Sum of all prime jump sizes; equals ∑P(k) for k ≥ 2 |
| D₀ ≈ 0.551691597558 | Log-Derivative Base | D(0) before any prime saturates |
| T ≈ 0.221463371375 | Correction Term | Algebraic gap; J = D₀ + T exactly |

The identity **J = D₀ + T** holds algebraically, prime by prime, via the partial fraction decomposition of 1/(p(p−1)).

J also encodes every prime zeta value simultaneously:

$$J = \sum_{p} \frac{1}{p(p-1)} = \sum_{k=2}^{\infty} P(k)$$

### Origin of C

The constant C was first identified in the broader Modular Lifting Rings framework, documented at [**wessengetachew.github.io/Zeta/**](https://wessengetachew.github.io/Zeta/). The key identity is:

$$C = \zeta(2) \cdot d_{FT} = \frac{\pi^2}{6} \cdot \prod_p \left(1 - \frac{2}{p^2}\right) \approx 0.530711806246\ldots$$

The numerical value is recorded in OEIS as **A065469** (density of consecutive squarefree pairs, Tóth–Sándor 1989). What is new here is the geometric interpretation: C is the long-run fraction of coprime residues on ring M that survive the lift to ring M+1, verified empirically to M = 2,000,000. The framework was not invented but discovered — the geometry of the modular rings was already there.

---

## Interactive Features

The HTML file (`jump_theorem-4-1.html`) is a self-contained, zero-dependency interactive document. Open it in any modern browser.

### Tabs & Tools

- **Ring Explorer** — Visualize coprime residues in modular ring M as a circular diagram. Toggle M to watch the structure change at prime vs. composite values.
- **Lift Visualizer** — Animate the lift from ring M to M+1. Watch residues survive or break as the ring grows.
- **Jump Theorem Prime Checker** — Enter any integer n ≥ 1:
  - Computes C(n−1) and C(n)
  - Detects whether D(x) jumps at x = n−1
  - Recovers the prime from the jump size and verifies the discriminant
  - **Display modes:** Scientific notation · Exact fraction · Relative to p=2 · Ring geometry
  - **Export:** Downloads a 4-panel PNG of all views for any n
- **Jump Spectrum Canvas** — Live plot of C(x), D(x), and the jump spectrum on a log scale
- **Preset buttons** — φ boundary (n=1), p=2, 3, 7, 11, 101, 9999991, 10⁹+7

### Special Input: n = 1

Enter n = 1 to explore the golden ratio φ as the phantom boundary of the spectrum. The discriminant is 5 (not a square), the recovery formula returns φ, and the document traces the full breakdown of integer recovery at this irrational threshold.

---

## Usage

```
# No build step required. Just open the file.
open jump_theorem-4-1.html
```

Or serve locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000/jump_theorem-4-1.html
```

**Dependencies (loaded from CDN):**
- [MathJax 3](https://www.mathjax.org/) — LaTeX rendering
- [Cormorant Garamond, EB Garamond, JetBrains Mono](https://fonts.google.com/) — Typography

No npm, no bundler, no framework. Pure HTML/CSS/JS.

---

## Context

This document is **Layer 05** of a multi-part exposition titled *The Lift Survival Function*. The broader project spans modular arithmetic geometry, analytic number theory, and interactive visualization. All pieces are self-contained HTML files — open any in a browser, no install required.

### The Lift Survival Function (main)
🔗 [wessengetachew.github.io/Sierpi-ski/](https://wessengetachew.github.io/Sierpi-ski/)

### This tool
🔗 [wessengetachew.github.io/Jump/](https://wessengetachew.github.io/Jump/) — Jump Theorem Prime Checker (this repo)

### Related interactive works

| Link | Topic |
|------|-------|
| [Zeta](https://wessengetachew.github.io/Zeta/) | Origin of C; Modular Lifting Rings framework and the identity C = ζ(2)·d_FT |
| [2025](https://wessengetachew.github.io/2025/) | Collected work 2025 |
| [Transform](https://wessengetachew.github.io/Transform/) | Transform methods |
| [Finite](https://wessengetachew.github.io/finite/) | Finite structures |
| [Primes](https://wessengetachew.github.io/Primes/) | Prime visualizations |
| [Farey](https://wessengetachew.github.io/Farey/) | Farey sequences |
| [Composite](https://wessengetachew.github.io/Composite/) | Composite number structure |
| [Ethiopian](https://wessengetachew.github.io/Ethiopian/) | Ethiopian mathematics |
| [2πr](https://wessengetachew.github.io/2pir/) | Circle geometry |
| [Rational](https://wessengetachew.github.io/Rational-/) | Rational approximations |
| [Infinite Moduli](https://wessengetachew.github.io/Infinitemoduli/) | Infinite modular systems |
| [Pythagorean](https://wessengetachew.github.io/Pythagorean-/) | Pythagorean structure |
| [Phase](https://wessengetachew.github.io/Phase/) | Phase analysis |
| [Gemini](https://wessengetachew.github.io/Gemini/) | Twin prime geometry |
| [Rebuild](https://wessengetachew.github.io/Rebuild/) | Reconstruction methods |
| [Goldbach](https://wessengetachew.github.io/Goldbach/) | Goldbach conjecture explorations |

---

## Author

**W. Getachew** · 2026 · math.NT

*The Lift Survival Function — Where primes reveal themselves as exact discontinuities in a smooth Euler product.*

---

## License

Research exposition. Please cite if you build on this work.
