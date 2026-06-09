# __imp_load_CreateFileW

- ea: `0x18000ea96`
- end: `0x18000eaa2`
- name: `__imp_load_CreateFileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callees

- `0x18000ea17`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ea96`

## pseudocode

```c
__int64 load_CreateFileW()
{
  return _tailMerge_api_ms_win_core_file_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ea96  lea     rax, __imp_CreateFileW
0x18000ea9d  jmp     __tailMerge_api_ms_win_core_file_l1_1_0_dll
```
