# System.Range::.ctor

- ea: `0x3c0`
- end: `0x3cf`
- name: `System.Range::.ctor`
- size: `15`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x4b0`
- `0x4c0`
- `0x4d0`

## pseudocode

```c

```

## disassembly

```asm
0x3c0  ldarg.0
0x3c1  ldarg.1
0x3c2  stfld    valuetype System.Index System.Range::<Start>k__BackingField
0x3c7  ldarg.0
0x3c8  ldarg.2
0x3c9  stfld    valuetype System.Index System.Range::<End>k__BackingField
0x3ce  ret
```
