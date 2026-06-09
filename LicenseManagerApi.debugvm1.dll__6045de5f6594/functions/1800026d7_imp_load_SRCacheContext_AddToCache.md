# __imp_load_SRCacheContext_AddToCache

- ea: `0x1800026d7`
- end: `0x1800026e3`
- name: `__imp_load_SRCacheContext_AddToCache`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002658`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800026d7`

## pseudocode

```c
__int64 load_SRCacheContext_AddToCache()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll();
}

```

## disassembly

```asm
0x1800026d7  lea     rax, __imp_SRCacheContext_AddToCache
0x1800026de  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll
```
