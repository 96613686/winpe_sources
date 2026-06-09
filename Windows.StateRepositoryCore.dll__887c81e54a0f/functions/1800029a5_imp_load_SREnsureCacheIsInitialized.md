# __imp_load_SREnsureCacheIsInitialized

- ea: `0x1800029a5`
- end: `0x1800029b1`
- name: `__imp_load_SREnsureCacheIsInitialized`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002926`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-6!SREnsureCacheIsInitialized` at `0x1800029a5`

## pseudocode

```c
__int64 load_SREnsureCacheIsInitialized()
{
  return _tailMerge_ext_ms_onecore_appmodel_staterepository_internal_l1_1_6_dll();
}

```

## disassembly

```asm
0x1800029a5  lea     rax, __imp_SREnsureCacheIsInitialized
0x1800029ac  jmp     __tailMerge_ext_ms_onecore_appmodel_staterepository_internal_l1_1_6_dll
```
