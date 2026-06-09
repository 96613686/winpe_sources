# __imp_load_ImpersonateLoggedOnUser

- ea: `0x18000def2`
- end: `0x18000defe`
- name: `__imp_load_ImpersonateLoggedOnUser`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000dd6a`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000def2`

## pseudocode

```c
__int64 load_ImpersonateLoggedOnUser()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000def2  lea     rax, __imp_ImpersonateLoggedOnUser
0x18000def9  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
