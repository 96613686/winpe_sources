# __imp_load_SRCacheContext_Open

- ea: `0x180002604`
- end: `0x180002610`
- name: `__imp_load_SRCacheContext_Open`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002561`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180002604`

## pseudocode

```c
__int64 load_SRCacheContext_Open()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002604  lea     rax, __imp_SRCacheContext_Open
0x18000260b  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
