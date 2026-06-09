# __imp_load_InitializeSecurityDescriptor

- ea: `0x1800023b8`
- end: `0x1800023c4`
- name: `__imp_load_InitializeSecurityDescriptor`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800023b8`

## pseudocode

```c
__int64 load_InitializeSecurityDescriptor()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x1800023b8  lea     rax, __imp_InitializeSecurityDescriptor
0x1800023bf  jmp     __tailMerge_advapi32_dll
```
