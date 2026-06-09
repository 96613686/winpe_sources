# __imp_load_IsValidSecurityDescriptor

- ea: `0x1800023dc`
- end: `0x1800023e8`
- name: `__imp_load_IsValidSecurityDescriptor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800023dc`

## pseudocode

```c
__int64 load_IsValidSecurityDescriptor()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800023dc  lea     rax, __imp_IsValidSecurityDescriptor
0x1800023e3  jmp     __tailMerge_advapi32_dll
```
