# __imp_load_InitializeAcl

- ea: `0x180002382`
- end: `0x18000238e`
- name: `__imp_load_InitializeAcl`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fff`

## import_xrefs

- `ADVAPI32!InitializeAcl` at `0x180002382`

## pseudocode

```c
__int64 load_InitializeAcl()
{
  return _tailMerge_advapi32_dll();
}

```

## disassembly

```asm
0x180002382  lea     rax, __imp_InitializeAcl
0x180002389  jmp     __tailMerge_advapi32_dll
```
