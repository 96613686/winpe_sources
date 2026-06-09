# __imp_load_DirectUIInitThread

- ea: `0x1800091eb`
- end: `0x1800091f7`
- name: `__imp_load_DirectUIInitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009136`

## import_xrefs

- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIInitThread` at `0x1800091eb`

## pseudocode

```c
__int64 load_DirectUIInitThread()
{
  return _tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800091eb  lea     rax, __imp_DirectUIInitThread
0x1800091f2  jmp     __tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll
```
