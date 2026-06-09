# __imp_load_CreateWndMgmt

- ea: `0x1800091b5`
- end: `0x1800091c1`
- name: `__imp_load_CreateWndMgmt`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180009136`

## import_xrefs

- `ext-ms-win-security-authbrokerui-l1-1-0!CreateWndMgmt` at `0x1800091b5`

## pseudocode

```c
__int64 load_CreateWndMgmt()
{
  return _tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800091b5  lea     rax, __imp_CreateWndMgmt
0x1800091bc  jmp     __tailMerge_ext_ms_win_security_authbrokerui_l1_1_0_dll
```
