# __imp_load_GetSecurityDescriptorOwner

- ea: `0x18000a728`
- end: `0x18000a734`
- name: `__imp_load_GetSecurityDescriptorOwner`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18000a728`

## pseudocode

```c
__int64 load_GetSecurityDescriptorOwner()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a728  lea     rax, __imp_GetSecurityDescriptorOwner
0x18000a72f  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
