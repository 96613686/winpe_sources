# __imp_load_Int_FwValidateComplianceAndReduceConnSecRuleToVersion

- ea: `0x180020502`
- end: `0x18002050e`
- name: `__imp_load_Int_FwValidateComplianceAndReduceConnSecRuleToVersion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FwValidateComplianceAndReduceConnSecRuleToVersion` at `0x180020502`

## pseudocode

```c
__int64 load_Int_FwValidateComplianceAndReduceConnSecRuleToVersion()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020502  lea     rax, __imp_Int_FwValidateComplianceAndReduceConnSecRuleToVersion
0x180020509  jmp     __tailMerge_fwbase_dll
```
