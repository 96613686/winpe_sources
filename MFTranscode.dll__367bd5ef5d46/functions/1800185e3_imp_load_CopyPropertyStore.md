# __imp_load_CopyPropertyStore

- ea: `0x1800185e3`
- end: `0x1800185ef`
- name: `__imp_load_CopyPropertyStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180018564`

## import_xrefs

- `MFCORE!CopyPropertyStore` at `0x1800185e3`

## pseudocode

```c
__int64 load_CopyPropertyStore()
{
  return _tailMerge_mfcore_dll();
}

```

## disassembly

```asm
0x1800185e3  lea     rax, __imp_CopyPropertyStore
0x1800185ea  jmp     __tailMerge_mfcore_dll
```
