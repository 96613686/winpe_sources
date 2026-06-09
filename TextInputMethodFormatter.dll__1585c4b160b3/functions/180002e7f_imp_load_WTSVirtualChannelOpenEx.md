# __imp_load_WTSVirtualChannelOpenEx

- ea: `0x180002e7f`
- end: `0x180002e8b`
- name: `__imp_load_WTSVirtualChannelOpenEx`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002dca`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelOpenEx` at `0x180002e7f`

## pseudocode

```c
__int64 load_WTSVirtualChannelOpenEx()
{
  return _tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002e7f  lea     rax, __imp_WTSVirtualChannelOpenEx
0x180002e86  jmp     __tailMerge_ext_ms_win_session_wtsapi32_l1_1_0_dll
```
