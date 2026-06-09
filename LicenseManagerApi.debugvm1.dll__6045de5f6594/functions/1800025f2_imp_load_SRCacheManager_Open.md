# __imp_load_SRCacheManager_Open

- ea: `0x1800025f2`
- end: `0x1800025fe`
- name: `__imp_load_SRCacheManager_Open`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002561`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800025f2`

## pseudocode

```c
__int64 load_SRCacheManager_Open()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800025f2  lea     rax, __imp_SRCacheManager_Open
0x1800025f9  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
