# __imp_load_LookupAccountSidLocalW

- ea: `0x1800103bb`
- end: `0x1800103c7`
- name: `__imp_load_LookupAccountSidLocalW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001033c`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800103bb`

## pseudocode

```c
__int64 load_LookupAccountSidLocalW()
{
  return _tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800103bb  lea     rax, __imp_LookupAccountSidLocalW
0x1800103c2  jmp     __tailMerge_api_ms_win_security_lsalookup_l1_1_0_dll
```
