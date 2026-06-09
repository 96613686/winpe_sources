# __imp_load_SHCreateStreamOnFileW

- ea: `0x180002525`
- end: `0x180002531`
- name: `__imp_load_SHCreateStreamOnFileW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024a6`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180002525`

## pseudocode

```c
__int64 load_SHCreateStreamOnFileW()
{
  return _tailMerge_api_ms_win_shcore_stream_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002525  lea     rax, __imp_SHCreateStreamOnFileW
0x18000252c  jmp     __tailMerge_api_ms_win_shcore_stream_l1_1_0_dll
```
