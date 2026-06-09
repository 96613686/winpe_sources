# __imp_load_CreatePropertyStore

- ea: `0x180018407`
- end: `0x180018413`
- name: `__imp_load_CreatePropertyStore`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001828c`

## import_xrefs

- `MFPlat!CreatePropertyStore` at `0x180018407`

## pseudocode

```c
__int64 load_CreatePropertyStore()
{
  return _tailMerge_mfplat_dll();
}

```

## disassembly

```asm
0x180018407  lea     rax, __imp_CreatePropertyStore
0x18001840e  jmp     __tailMerge_mfplat_dll
```
