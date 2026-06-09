# __imp_load_SRCacheContext_GetField_UInt64

- ea: `0x180003b6d`
- end: `0x180003b79`
- name: `__imp_load_SRCacheContext_GetField_UInt64`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a09`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x180003b6d`

## pseudocode

```c
__int64 load_SRCacheContext_GetField_UInt64()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003b6d  lea     rax, __imp_SRCacheContext_GetField_UInt64
0x180003b74  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
