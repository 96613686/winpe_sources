# __imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW

- ea: `0x18000207e`
- end: `0x18000208a`
- name: `__imp_load_ConvertStringSecurityDescriptorToSecurityDescriptorW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000207e`

## pseudocode

```c
__int64 load_ConvertStringSecurityDescriptorToSecurityDescriptorW()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x18000207e  lea     rax, __imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180002085  jmp     __tailMerge_advapi32_dll
```
