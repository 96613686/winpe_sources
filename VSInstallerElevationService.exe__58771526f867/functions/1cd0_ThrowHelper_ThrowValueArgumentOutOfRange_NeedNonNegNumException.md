# ThrowHelper::ThrowValueArgumentOutOfRange_NeedNonNegNumException

- ea: `0x1cd0`
- end: `0x1ce0`
- name: `ThrowHelper::ThrowValueArgumentOutOfRange_NeedNonNegNumException`
- size: `16`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0xe0`
- `0x130`
- `0x140`

## pseudocode

```c

```

## disassembly

```asm
0x1cd0  ldstr    aValue// "value"
0x1cd5  ldstr    aNonNegativeNum// "Non-negative number required."
0x1cda  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0x1cdf  throw
```
