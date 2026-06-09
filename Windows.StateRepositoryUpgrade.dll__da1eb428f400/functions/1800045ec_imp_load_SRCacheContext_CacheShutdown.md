# __imp_load_SRCacheContext_CacheShutdown

- ea: `0x1800045ec`
- end: `0x1800045f8`
- name: `__imp_load_SRCacheContext_CacheShutdown`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000456d`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_CacheShutdown` at `0x1800045ec`

## pseudocode

```c
__int64 load_SRCacheContext_CacheShutdown()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll();
}

```

## disassembly

```asm
0x1800045ec  lea     rax, __imp_SRCacheContext_CacheShutdown
0x1800045f3  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_4_dll
```
