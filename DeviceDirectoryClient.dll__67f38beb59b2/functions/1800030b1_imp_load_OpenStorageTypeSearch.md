# __imp_load_OpenStorageTypeSearch

- ea: `0x1800030b1`
- end: `0x1800030bd`
- name: `__imp_load_OpenStorageTypeSearch`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003032`

## import_xrefs

- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x1800030b1`

## pseudocode

```c
__int64 load_OpenStorageTypeSearch()
{
  return _tailMerge_ext_ms_win_storage_sense_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800030b1  lea     rax, __imp_OpenStorageTypeSearch
0x1800030b8  jmp     __tailMerge_ext_ms_win_storage_sense_l1_1_0_dll
```
