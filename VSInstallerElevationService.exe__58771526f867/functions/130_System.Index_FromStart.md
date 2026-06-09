# System.Index::FromStart

- ea: `0x130`
- end: `0x140`
- name: `System.Index::FromStart`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1f0`

## callees

- `0x100`
- `0x130`
- `0x1cd0`

## pseudocode

```c

```

## disassembly

```asm
0x130  ldarg.0
0x131  ldc.i4.0
0x132  bge.s    loc_139
0x134  call     void ThrowHelper::ThrowValueArgumentOutOfRange_NeedNonNegNumException()
0x139  ldarg.0
0x13a  newobj   instance void System.Index::.ctor(int32 value)
0x13f  ret
```
