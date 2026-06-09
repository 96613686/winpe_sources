# __imp_load_PathFileExistsW

- ea: `0x180045595`
- end: `0x1800455a1`
- name: `__imp_load_PathFileExistsW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180045516`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180045595`

## pseudocode

```c
__int64 load_PathFileExistsW()
{
  return _tailMerge_api_ms_win_core_shlwapi_legacy_l1_1_0_dll();
}

```

## disassembly

```asm
0x180045595  lea     rax, __imp_PathFileExistsW
0x18004559c  jmp     __tailMerge_api_ms_win_core_shlwapi_legacy_l1_1_0_dll
```
