# __imp_load_SetSecurityDescriptorDacl

- ea: `0x18000a7dc`
- end: `0x18000a7e8`
- name: `__imp_load_SetSecurityDescriptorDacl`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000a7dc`

## pseudocode

```c
__int64 load_SetSecurityDescriptorDacl()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a7dc  lea     rax, __imp_SetSecurityDescriptorDacl
0x18000a7e3  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
