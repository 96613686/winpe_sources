# __imp_load_GetSecurityDescriptorLength

- ea: `0x18000a7ee`
- end: `0x18000a7fa`
- name: `__imp_load_GetSecurityDescriptorLength`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000a7ee`

## pseudocode

```c
__int64 load_GetSecurityDescriptorLength()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a7ee  lea     rax, __imp_GetSecurityDescriptorLength
0x18000a7f5  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
