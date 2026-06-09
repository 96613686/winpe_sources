# __imp_load_LsaManageSidNameMapping

- ea: `0x14000445f`
- end: `0x14000446b`
- name: `__imp_load_LsaManageSidNameMapping`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400043e0`

## import_xrefs

- `api-ms-win-security-lsalookup-l2-1-1!LsaManageSidNameMapping` at `0x14000445f`

## pseudocode

```c
__int64 load_LsaManageSidNameMapping()
{
  return _tailMerge_api_ms_win_security_lsalookup_l2_1_1_dll();
}

```

## disassembly

```asm
0x14000445f  lea     rax, __imp_LsaManageSidNameMapping
0x140004466  jmp     __tailMerge_api_ms_win_security_lsalookup_l2_1_1_dll
```
