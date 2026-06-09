# __imp_load_InitializeSecurityDescriptor

- ea: `0x18000a75e`
- end: `0x18000a76a`
- name: `__imp_load_InitializeSecurityDescriptor`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a697`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000a75e`

## pseudocode

```c
__int64 load_InitializeSecurityDescriptor()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000a75e  lea     rax, __imp_InitializeSecurityDescriptor
0x18000a765  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
