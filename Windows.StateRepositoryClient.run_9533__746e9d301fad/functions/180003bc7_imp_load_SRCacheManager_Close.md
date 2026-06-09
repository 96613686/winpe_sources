# __imp_load_SRCacheManager_Close

- ea: `0x180003bc7`
- end: `0x180003bd3`
- name: `__imp_load_SRCacheManager_Close`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a09`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180003bc7`

## pseudocode

```c
__int64 load_SRCacheManager_Close()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003bc7  lea     rax, __imp_SRCacheManager_Close
0x180003bce  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
