# __imp_load_LookupAccountSidW

- ea: `0x18002b120`
- end: `0x18002b12c`
- name: `__imp_load_LookupAccountSidW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002b0a1`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002b120`

## pseudocode

```c
__int64 load_LookupAccountSidW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll();
}

```

## disassembly

```asm
0x18002b120  lea     rax, __imp_LookupAccountSidW
0x18002b127  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_0_dll
```
