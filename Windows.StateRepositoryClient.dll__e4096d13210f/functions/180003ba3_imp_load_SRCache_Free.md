# __imp_load_SRCache_Free

- ea: `0x180003ba3`
- end: `0x180003baf`
- name: `__imp_load_SRCache_Free`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a09`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180003ba3`

## pseudocode

```c
__int64 load_SRCache_Free()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll();
}

```

## disassembly

```asm
0x180003ba3  lea     rax, __imp_SRCache_Free
0x180003baa  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_cache_l1_1_0_dll
```
