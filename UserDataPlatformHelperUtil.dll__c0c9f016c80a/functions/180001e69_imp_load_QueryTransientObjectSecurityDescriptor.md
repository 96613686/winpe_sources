# __imp_load_QueryTransientObjectSecurityDescriptor

- ea: `0x180001e69`
- end: `0x180001e75`
- name: `__imp_load_QueryTransientObjectSecurityDescriptor`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001dea`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180001e69`

## pseudocode

```c
__int64 load_QueryTransientObjectSecurityDescriptor()
{
  return _tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll();
}

```

## disassembly

```asm
0x180001e69  lea     rax, __imp_QueryTransientObjectSecurityDescriptor
0x180001e70  jmp     __tailMerge_api_ms_win_security_accesshlpr_l1_1_0_dll
```
