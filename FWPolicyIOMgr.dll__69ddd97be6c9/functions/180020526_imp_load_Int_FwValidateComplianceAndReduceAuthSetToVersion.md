# __imp_load_Int_FwValidateComplianceAndReduceAuthSetToVersion

- ea: `0x180020526`
- end: `0x180020532`
- name: `__imp_load_Int_FwValidateComplianceAndReduceAuthSetToVersion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FwValidateComplianceAndReduceAuthSetToVersion` at `0x180020526`

## pseudocode

```c
__int64 load_Int_FwValidateComplianceAndReduceAuthSetToVersion()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020526  lea     rax, __imp_Int_FwValidateComplianceAndReduceAuthSetToVersion
0x18002052d  jmp     __tailMerge_fwbase_dll
```
