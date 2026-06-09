# __imp_load_SRCacheContext_GetField_Binary

- ea: `0x180003bd9`
- end: `0x180003be5`
- name: `__imp_load_SRCacheContext_GetField_Binary`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003ab8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180003bd9`

## pseudocode

```c
__int64 load_SRCacheContext_GetField_Binary()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll();
}

```

## disassembly

```asm
0x180003bd9  lea     rax, __imp_SRCacheContext_GetField_Binary
0x180003be0  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll
```
