# __imp_load_PathFileExistsW

- ea: `0x140002996`
- end: `0x1400029a2`
- name: `__imp_load_PathFileExistsW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x140002905`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x140002996`

## pseudocode

```c
__int64 load_PathFileExistsW()
{
  return _tailMerge_api_ms_win_core_shlwapi_legacy_l1_1_0_dll();
}

```

## disassembly

```asm
0x140002996  lea     rax, __imp_PathFileExistsW
0x14000299d  jmp     __tailMerge_api_ms_win_core_shlwapi_legacy_l1_1_0_dll
```
