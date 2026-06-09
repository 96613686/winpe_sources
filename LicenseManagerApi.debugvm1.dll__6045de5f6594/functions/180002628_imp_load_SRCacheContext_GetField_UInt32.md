# __imp_load_SRCacheContext_GetField_UInt32

- ea: `0x180002628`
- end: `0x180002634`
- name: `__imp_load_SRCacheContext_GetField_UInt32`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002561`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180002628`

## pseudocode

```c
__int64 load_SRCacheContext_GetField_UInt32()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002628  lea     rax, __imp_SRCacheContext_GetField_UInt32
0x18000262f  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
