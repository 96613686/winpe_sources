# __imp_load_SRCacheContext_Close

- ea: `0x1800026fb`
- end: `0x180002707`
- name: `__imp_load_SRCacheContext_Close`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002561`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800026fb`

## pseudocode

```c
__int64 load_SRCacheContext_Close()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800026fb  lea     rax, __imp_SRCacheContext_Close
0x180002702  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
