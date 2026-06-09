# __imp_load_SetUserObjectSecurity

- ea: `0x1800096eb`
- end: `0x1800096f7`
- name: `__imp_load_SetUserObjectSecurity`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000966c`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-usersecurity-l1-1-0!SetUserObjectSecurity` at `0x1800096eb`

## pseudocode

```c
__int64 load_SetUserObjectSecurity()
{
  return _tailMerge_ext_ms_win_rtcore_ntuser_usersecurity_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800096eb  lea     rax, __imp_SetUserObjectSecurity
0x1800096f2  jmp     __tailMerge_ext_ms_win_rtcore_ntuser_usersecurity_l1_1_0_dll
```
