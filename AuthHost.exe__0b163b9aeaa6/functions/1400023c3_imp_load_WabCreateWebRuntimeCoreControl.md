# __imp_load_WabCreateWebRuntimeCoreControl

- ea: `0x1400023c3`
- end: `0x1400023cf`
- name: `__imp_load_WabCreateWebRuntimeCoreControl`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140002332`

## import_xrefs

- `ext-ms-win-security-authbrokerui-l1-1-0!WabCreateWebRuntimeCoreControl` at `0x1400023c3`

## pseudocode

```c
__int64 load_WabCreateWebRuntimeCoreControl()
{
  return _tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll();
}

```

## disassembly

```asm
0x1400023c3  lea     rax, __imp_WabCreateWebRuntimeCoreControl
0x1400023ca  jmp     __tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll
```
