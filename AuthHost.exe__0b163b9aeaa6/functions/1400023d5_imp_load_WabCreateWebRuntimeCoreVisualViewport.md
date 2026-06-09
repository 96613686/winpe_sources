# __imp_load_WabCreateWebRuntimeCoreVisualViewport

- ea: `0x1400023d5`
- end: `0x1400023e1`
- name: `__imp_load_WabCreateWebRuntimeCoreVisualViewport`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002332`

## import_xrefs

- `ext-ms-win-security-authbrokerui-l1-1-0!WabCreateWebRuntimeCoreVisualViewport` at `0x1400023d5`

## pseudocode

```c
__int64 load_WabCreateWebRuntimeCoreVisualViewport()
{
  return _tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400023d5  lea     rax, __imp_WabCreateWebRuntimeCoreVisualViewport
0x1400023dc  jmp     __tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll
```
