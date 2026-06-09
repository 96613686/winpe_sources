# __imp_load_FDICopy

- ea: `0x180002279`
- end: `0x180002285`
- name: `__imp_load_FDICopy`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800021e8`

## import_xrefs

- `Cabinet!__imp_FDICopy` at `0x180002279`

## pseudocode

```c
__int64 load_FDICopy()
{
  return _tailMerge_cabinet_dll();
}

```

## disassembly

```asm
0x180002279  lea     rax, __imp_FDICopy
0x180002280  jmp     __tailMerge_cabinet_dll
```
