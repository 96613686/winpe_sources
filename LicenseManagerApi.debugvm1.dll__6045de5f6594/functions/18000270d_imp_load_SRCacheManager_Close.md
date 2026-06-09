# __imp_load_SRCacheManager_Close

- ea: `0x18000270d`
- end: `0x180002719`
- name: `__imp_load_SRCacheManager_Close`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002561`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000270d`

## pseudocode

```c
__int64 load_SRCacheManager_Close()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000270d  lea     rax, __imp_SRCacheManager_Close
0x180002714  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
