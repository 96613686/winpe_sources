# __imp_load_SetSecurityDescriptorGroup

- ea: `0x18000a782`
- end: `0x18000a78e`
- name: `__imp_load_SetSecurityDescriptorGroup`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x18000a782`

## pseudocode

```c
__int64 load_SetSecurityDescriptorGroup()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a782  lea     rax, __imp_SetSecurityDescriptorGroup
0x18000a789  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
