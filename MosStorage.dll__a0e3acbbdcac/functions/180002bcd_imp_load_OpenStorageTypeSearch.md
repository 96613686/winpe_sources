# __imp_load_OpenStorageTypeSearch

- ea: `0x180002bcd`
- end: `0x180002bd9`
- name: `__imp_load_OpenStorageTypeSearch`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002b06`

## import_xrefs

- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x180002bcd`

## pseudocode

```c
__int64 load_OpenStorageTypeSearch()
{
  return _tailMerge_ext_ms_win_storage_sense_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002bcd  lea     rax, __imp_OpenStorageTypeSearch
0x180002bd4  jmp     __tailMerge_ext_ms_win_storage_sense_l1_1_0_dll
```
