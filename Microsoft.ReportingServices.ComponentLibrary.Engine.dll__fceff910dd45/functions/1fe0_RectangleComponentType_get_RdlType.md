# RectangleComponentType::get_RdlType

- ea: `0x1fe0`
- end: `0x1feb`
- name: `RectangleComponentType::get_RdlType`
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
0x1fe0  ldtoken  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Rectangle
0x1fe5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fea  ret
```
