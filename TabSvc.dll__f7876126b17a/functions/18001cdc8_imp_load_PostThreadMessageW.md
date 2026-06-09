# __imp_load_PostThreadMessageW

- ea: `0x18001cdc8`
- end: `0x18001cdd4`
- name: `__imp_load_PostThreadMessageW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001cd49`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostThreadMessageW` at `0x18001cdc8`

## pseudocode

```c
__int64 load_PostThreadMessageW()
{
  return _tailMerge_api_ms_win_rtcore_ntuser_window_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001cdc8  lea     rax, __imp_PostThreadMessageW
0x18001cdcf  jmp     __tailMerge_api_ms_win_rtcore_ntuser_window_l1_1_0_dll
```
