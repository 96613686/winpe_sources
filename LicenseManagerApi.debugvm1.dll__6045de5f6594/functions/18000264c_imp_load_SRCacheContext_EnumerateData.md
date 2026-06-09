# __imp_load_SRCacheContext_EnumerateData

- ea: `0x18000264c`
- end: `0x180002658`
- name: `__imp_load_SRCacheContext_EnumerateData`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002561`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000264c`

## pseudocode

```c
__int64 load_SRCacheContext_EnumerateData()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000264c  lea     rax, __imp_SRCacheContext_EnumerateData
0x180002653  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
