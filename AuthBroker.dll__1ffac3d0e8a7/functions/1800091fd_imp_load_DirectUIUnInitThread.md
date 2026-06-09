# __imp_load_DirectUIUnInitThread

- ea: `0x1800091fd`
- end: `0x180009209`
- name: `__imp_load_DirectUIUnInitThread`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009136`

## import_xrefs

- `ext-ms-win-security-authbrokerui-l1-1-0!DirectUIUnInitThread` at `0x1800091fd`

## pseudocode

```c
__int64 load_DirectUIUnInitThread()
{
  return _tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800091fd  lea     rax, __imp_DirectUIUnInitThread
0x180009204  jmp     __tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll
```
