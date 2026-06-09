# __imp_load_InitPropVariantFromCLSID

- ea: `0x180010178`
- end: `0x180010184`
- name: `__imp_load_InitPropVariantFromCLSID`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800100d5`

## import_xrefs

- `PROPSYS!InitPropVariantFromCLSID` at `0x180010178`

## pseudocode

```c
__int64 load_InitPropVariantFromCLSID()
{
  return _tailMerge_propsys_dll();
}

```

## disassembly

```asm
0x180010178  lea     rax, __imp_InitPropVariantFromCLSID
0x18001017f  jmp     __tailMerge_propsys_dll
```
