# __imp_load_Int_FwValidateComplianceAndReduceMainModeRuleToVersion

- ea: `0x180020514`
- end: `0x180020520`
- name: `__imp_load_Int_FwValidateComplianceAndReduceMainModeRuleToVersion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FwValidateComplianceAndReduceMainModeRuleToVersion` at `0x180020514`

## pseudocode

```c
__int64 load_Int_FwValidateComplianceAndReduceMainModeRuleToVersion()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x180020514  lea     rax, __imp_Int_FwValidateComplianceAndReduceMainModeRuleToVersion
0x18002051b  jmp     __tailMerge_fwbase_dll
```
