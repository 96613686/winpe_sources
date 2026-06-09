# __imp_load_SRCacheManager_Open

- ea: `0x180003a9a`
- end: `0x180003aa6`
- name: `__imp_load_SRCacheManager_Open`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a09`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x180003a9a`

## pseudocode

```c
__int64 load_SRCacheManager_Open()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003a9a  lea     rax, __imp_SRCacheManager_Open
0x180003aa1  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
