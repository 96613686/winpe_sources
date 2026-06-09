# ChartComponentType::get_RdlType

- ea: `0x1f50`
- end: `0x1f5b`
- name: `ChartComponentType::get_RdlType`
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
0x1f50  ldtoken  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Chart
0x1f55  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f5a  ret
```
