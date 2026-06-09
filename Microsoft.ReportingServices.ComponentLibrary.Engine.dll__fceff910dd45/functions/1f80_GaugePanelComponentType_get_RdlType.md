# GaugePanelComponentType::get_RdlType

- ea: `0x1f80`
- end: `0x1f8b`
- name: `GaugePanelComponentType::get_RdlType`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1f80  ldtoken  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.GaugePanel
0x1f85  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f8a  ret
```
