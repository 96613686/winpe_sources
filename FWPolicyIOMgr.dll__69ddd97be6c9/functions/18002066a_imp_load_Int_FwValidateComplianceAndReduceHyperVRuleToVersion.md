# __imp_load_Int_FwValidateComplianceAndReduceHyperVRuleToVersion

- ea: `0x18002066a`
- end: `0x180020676`
- name: `__imp_load_Int_FwValidateComplianceAndReduceHyperVRuleToVersion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FwValidateComplianceAndReduceHyperVRuleToVersion` at `0x18002066a`

## pseudocode

```c
__int64 load_Int_FwValidateComplianceAndReduceHyperVRuleToVersion()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x18002066a  lea     rax, __imp_Int_FwValidateComplianceAndReduceHyperVRuleToVersion
0x180020671  jmp     __tailMerge_fwbase_dll
```
