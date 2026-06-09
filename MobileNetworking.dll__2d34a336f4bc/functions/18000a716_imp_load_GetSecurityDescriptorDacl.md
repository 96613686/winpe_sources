# __imp_load_GetSecurityDescriptorDacl

- ea: `0x18000a716`
- end: `0x18000a722`
- name: `__imp_load_GetSecurityDescriptorDacl`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000a716`

## pseudocode

```c
__int64 load_GetSecurityDescriptorDacl()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a716  lea     rax, __imp_GetSecurityDescriptorDacl
0x18000a71d  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
