# TablixComponentType::get_RdlType

- ea: `0x2010`
- end: `0x201b`
- name: `TablixComponentType::get_RdlType`
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
0x2010  ldtoken  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Tablix
0x2015  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x201a  ret
```
