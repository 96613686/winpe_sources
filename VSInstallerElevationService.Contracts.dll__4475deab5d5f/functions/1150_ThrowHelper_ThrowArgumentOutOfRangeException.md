# ThrowHelper::ThrowArgumentOutOfRangeException

- ea: `0x1150`
- end: `0x115b`
- name: `ThrowHelper::ThrowArgumentOutOfRangeException`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x390`

## pseudocode

```c

```

## disassembly

```asm
0x1150  ldstr    aLength// "length"
0x1155  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x115a  throw
```
