# __imp_load_FreeTransientObjectSecurityDescriptor

- ea: `0x180002160`
- end: `0x18000216c`
- name: `__imp_load_FreeTransientObjectSecurityDescriptor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002009`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180002160`

## pseudocode

```c
__int64 load_FreeTransientObjectSecurityDescriptor()
{
  return _tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll();
}

```

## disassembly

```asm
0x180002160  lea     rax, __imp_FreeTransientObjectSecurityDescriptor
0x180002167  jmp     __tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll
```
