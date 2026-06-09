# ThrowHelper::ThrowValueArgumentOutOfRange_NeedNonNegNumException

- ea: `0x39e0`
- end: `0x39f0`
- name: `ThrowHelper::ThrowValueArgumentOutOfRange_NeedNonNegNumException`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x230`
- `0x280`
- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x39e0  ldstr    aValue// "value"
0x39e5  ldstr    aNonNegativeNum// "Non-negative number required."
0x39ea  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x39ef  throw
```
