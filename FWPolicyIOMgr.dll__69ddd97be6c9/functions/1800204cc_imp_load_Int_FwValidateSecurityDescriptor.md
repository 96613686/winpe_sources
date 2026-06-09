# __imp_load_Int_FwValidateSecurityDescriptor

- ea: `0x1800204cc`
- end: `0x1800204d8`
- name: `__imp_load_Int_FwValidateSecurityDescriptor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FwValidateSecurityDescriptor` at `0x1800204cc`

## pseudocode

```c
__int64 load_Int_FwValidateSecurityDescriptor()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x1800204cc  lea     rax, __imp_Int_FwValidateSecurityDescriptor
0x1800204d3  jmp     __tailMerge_fwbase_dll
```
