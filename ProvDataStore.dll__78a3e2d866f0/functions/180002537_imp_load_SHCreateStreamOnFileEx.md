# __imp_load_SHCreateStreamOnFileEx

- ea: `0x180002537`
- end: `0x180002543`
- name: `__imp_load_SHCreateStreamOnFileEx`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024a6`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180002537`

## pseudocode

```c
__int64 load_SHCreateStreamOnFileEx()
{
  return _tailMerge_api_ms_win_shcore_stream_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002537  lea     rax, __imp_SHCreateStreamOnFileEx
0x18000253e  jmp     __tailMerge_api_ms_win_shcore_stream_l1_1_0_dll
```
