# __imp_load_FDICreate

- ea: `0x180002267`
- end: `0x180002273`
- name: `__imp_load_FDICreate`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800021e8`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x180002267`

## pseudocode

```c
__int64 load_FDICreate()
{
  return _tailMerge_cabinet_dll();
}

```

## disassembly

```asm
0x180002267  lea     rax, __imp_FDICreate
0x18000226e  jmp     __tailMerge_cabinet_dll
```
