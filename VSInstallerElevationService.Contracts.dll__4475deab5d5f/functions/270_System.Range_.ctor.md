# System.Range::.ctor

- ea: `0x270`
- end: `0x27f`
- name: `System.Range::.ctor`
- size: `15`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x360`
- `0x370`
- `0x380`

## pseudocode

```c

```

## disassembly

```asm
0x270  ldarg.0
0x271  ldarg.1
0x272  stfld    valuetype System.Index System.Range::<Start>k__BackingField
0x277  ldarg.0
0x278  ldarg.2
0x279  stfld    valuetype System.Index System.Range::<End>k__BackingField
0x27e  ret
```
