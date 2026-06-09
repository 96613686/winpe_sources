# __imp_load_SHCreateThread

- ea: `0x18000a45b`
- end: `0x18000a467`
- name: `__imp_load_SHCreateThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000a3dc`

## import_xrefs

- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18000a45b`

## pseudocode

```c
__int64 load_SHCreateThread()
{
  return _tailMerge_api_ms_win_shcore_thread_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a45b  lea     rax, __imp_SHCreateThread
0x18000a462  jmp     __tailMerge_api_ms_win_shcore_thread_l1_1_0_dll
```
