# __imp_load_GetExplicitEntriesFromAclW

- ea: `0x18000227e`
- end: `0x18000228a`
- name: `__imp_load_GetExplicitEntriesFromAclW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800021ff`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x18000227e`

## pseudocode

```c
__int64 load_GetExplicitEntriesFromAclW()
{
  return _tailMerge_api_ms_win_security_provider_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000227e  lea     rax, __imp_GetExplicitEntriesFromAclW
0x180002285  jmp     __tailMerge_api_ms_win_security_provider_l1_1_0_dll
```
