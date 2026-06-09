# __imp_load_SRCacheContext_GetField_String

- ea: `0x180003b7f`
- end: `0x180003b8b`
- name: `__imp_load_SRCacheContext_GetField_String`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a09`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180003b7f`

## pseudocode

```c
__int64 load_SRCacheContext_GetField_String()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003b7f  lea     rax, __imp_SRCacheContext_GetField_String
0x180003b86  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
