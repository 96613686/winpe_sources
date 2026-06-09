# __imp_load_Int_FwValidateComplianceAndReduceFirewallRuleToVersion

- ea: `0x1800204f0`
- end: `0x1800204fc`
- name: `__imp_load_Int_FwValidateComplianceAndReduceFirewallRuleToVersion`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800202d2`

## import_xrefs

- `fwbase!Int_FwValidateComplianceAndReduceFirewallRuleToVersion` at `0x1800204f0`

## pseudocode

```c
__int64 load_Int_FwValidateComplianceAndReduceFirewallRuleToVersion()
{
  return _tailMerge_fwbase_dll();
}

```

## disassembly

```asm
0x1800204f0  lea     rax, __imp_Int_FwValidateComplianceAndReduceFirewallRuleToVersion
0x1800204f7  jmp     __tailMerge_fwbase_dll
```
