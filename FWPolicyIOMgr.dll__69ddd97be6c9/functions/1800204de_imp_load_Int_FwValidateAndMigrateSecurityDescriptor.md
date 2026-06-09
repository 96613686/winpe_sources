# __imp_load_Int_FwValidateAndMigrateSecurityDescriptor

- ea: `0x1800204de`
- end: `0x1800204ea`
- name: `__imp_load_Int_FwValidateAndMigrateSecurityDescriptor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FwValidateAndMigrateSecurityDescriptor` at `0x1800204de`

## pseudocode

```c
__int64 load_Int_FwValidateAndMigrateSecurityDescriptor()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x1800204de  lea     rax, __imp_Int_FwValidateAndMigrateSecurityDescriptor
0x1800204e5  jmp     __tailMerge_fwbase_dll
```
