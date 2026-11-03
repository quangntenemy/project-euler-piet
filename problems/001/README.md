# Problem 001 — Multiples of 3 or 5

**Expected result:** `233168`

[Project Euler Problem 1](https://projecteuler.net/problem=1)

## Mathematical approach

We need the sum of all natural numbers below 1000 that are divisible by 3 or 5.

For multiples of `k`, let:

```text
n = floor(999 / k)
S(k) = k * n * (n + 1) / 2
```

Using inclusion-exclusion:

```text
S(3)  = 3  * 333 * 334 / 2 = 166833
S(5)  = 5  * 199 * 200 / 2 =  99500
S(15) = 15 *  66 *  67 / 2 =  33165

answer = S(3) + S(5) - S(15)
       = 166833 + 99500 - 33165
       = 233168
```

## Piet implementation

This problem is being developed through multiple attempts. The goal is not simply to produce a working Piet program, but to make the program itself a deliberate visual composition.

### Attempt 1 — Initial implementation

*Prototype · Online verification pending*

The first attempt uses an unrolled arithmetic-series calculation. It does not iterate through the numbers from 1 to 999.

The executable path is the sequence of colored blocks across the upper part of the image. Push values are encoded by the areas of their source blocks; arithmetic commands are encoded by the hue and lightness changes between adjacent blocks.

The initial image also includes a separate geometric composition. This was an early visual experiment, not part of the intended executed path.

**Known limitations and next steps:**

- The visual composition needs to be more intentional.
- The decorative filler should be removed.
- The program should be composed within a square canvas.
- The result still needs verification using the designated online interpreter.

#### Intended command sequence

The following is the conceptual sequence of operations the implementation is designed to perform. It is not a command trace captured from the official interpreter.

```text
push 3
push 333
multiply
push 334
multiply
push 2
divide                  -> 166833

push 5
push 199
multiply
push 200
multiply
push 2
divide                  -> 99500

add                     -> 266333

push 15
push 66
multiply
push 67
multiply
push 2
divide                  -> 33165

subtract                -> 233168
out(number)
```

The terminal block is shaped so that the interpreter can enter it for the output command, while all subsequent exits are intended to be blocked. This termination behavior remains subject to verification using the official interpreter.

### Attempt 2 — Square composition

*Planned · Not started*

The second attempt will revisit the visual design rather than simply crop or rearrange the first image.

**Design goals:**

- Use a square canvas.
- Remove the separate decorative filler.
- Make the executable Piet structure the central visual composition.
- Use negative space deliberately rather than filling it with unrelated shapes.
- Preserve the visual character of an intentional piece of artwork while maintaining valid Piet execution.

The mathematical solution may remain the same, but the visual arrangement and potentially the program layout will be reconsidered.

## Verification

| Check | Attempt 1 |
|---|---|
| Expected output | `233168` |
| Local execution-model check | Produced `233168` and terminated |
| Official online interpreter | Pending |
| Project status | Prototype |

The project's designated verification environment is [piet.gulla.net](https://piet.gulla.net/).

Neither attempt should be marked complete until the resulting Piet program has been executed successfully in that interpreter.

## Development notes

This is an iterative exploration. An attempt is a documented step in the process, not necessarily a final solution.

The objective is to find a balance between three things: mathematical correctness, valid Piet execution, and visual composition.