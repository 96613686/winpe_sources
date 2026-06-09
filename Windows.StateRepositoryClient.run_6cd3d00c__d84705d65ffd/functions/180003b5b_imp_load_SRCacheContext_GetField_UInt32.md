# __imp_load_SRCacheContext_GetField_UInt32

- ea: `0x180003b5b`
- end: `0x180003b67`
- name: `__imp_load_SRCacheContext_GetField_UInt32`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a09`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180003b5b`

## pseudocode

```c
__int64 load_SRCacheContext_GetField_UInt32()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003b5b  lea     rax, __imp_SRCacheContext_GetField_UInt32
0x180003b62  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
