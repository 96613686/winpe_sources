# __imp_load_SHCreateStreamOnFileW

- ea: `0x1800027ca`
- end: `0x1800027d6`
- name: `__imp_load_SHCreateStreamOnFileW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000274b`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x1800027ca`

## pseudocode

```c
__int64 load_SHCreateStreamOnFileW()
{
  return _tailMerge_api_ms_win_downlevel_shlwapi_l2_1_0_dll();
}

```

## disassembly

```asm
0x1800027ca  lea     rax, __imp_SHCreateStreamOnFileW
0x1800027d1  jmp     __tailMerge_api_ms_win_downlevel_shlwapi_l2_1_0_dll
```
