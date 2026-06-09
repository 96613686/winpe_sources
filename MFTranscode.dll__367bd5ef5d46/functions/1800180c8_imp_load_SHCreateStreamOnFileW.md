# __imp_load_SHCreateStreamOnFileW

- ea: `0x1800180c8`
- end: `0x1800180d4`
- name: `__imp_load_SHCreateStreamOnFileW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180018049`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x1800180c8`

## pseudocode

```c
__int64 load_SHCreateStreamOnFileW()
{
  return _tailMerge_api_ms_win_shcore_stream_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800180c8  lea     rax, __imp_SHCreateStreamOnFileW
0x1800180cf  jmp     __tailMerge_api_ms_win_shcore_stream_l1_1_0_dll
```
