# __imp_load_SetSecurityDescriptorDacl

- ea: `0x1800023ca`
- end: `0x1800023d6`
- name: `__imp_load_SetSecurityDescriptorDacl`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800023ca`

## pseudocode

```c
__int64 load_SetSecurityDescriptorDacl()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800023ca  lea     rax, __imp_SetSecurityDescriptorDacl
0x1800023d1  jmp     __tailMerge_advapi32_dll
```
