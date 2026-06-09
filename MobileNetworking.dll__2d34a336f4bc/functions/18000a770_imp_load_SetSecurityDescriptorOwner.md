# __imp_load_SetSecurityDescriptorOwner

- ea: `0x18000a770`
- end: `0x18000a77c`
- name: `__imp_load_SetSecurityDescriptorOwner`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18000a770`

## pseudocode

```c
__int64 load_SetSecurityDescriptorOwner()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a770  lea     rax, __imp_SetSecurityDescriptorOwner
0x18000a777  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
