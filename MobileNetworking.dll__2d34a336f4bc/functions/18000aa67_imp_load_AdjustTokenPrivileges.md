# __imp_load_AdjustTokenPrivileges

- ea: `0x18000aa67`
- end: `0x18000aa73`
- name: `__imp_load_AdjustTokenPrivileges`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000aa67`

## pseudocode

```c
__int64 load_AdjustTokenPrivileges()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000aa67  lea     rax, __imp_AdjustTokenPrivileges
0x18000aa6e  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
