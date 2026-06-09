# __imp_load_SRCacheContext_OpenSubContext

- ea: `0x180002616`
- end: `0x180002622`
- name: `__imp_load_SRCacheContext_OpenSubContext`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002561`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180002616`

## pseudocode

```c
__int64 load_SRCacheContext_OpenSubContext()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002616  lea     rax, __imp_SRCacheContext_OpenSubContext
0x18000261d  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
