# ImageComponentType::get_RdlType

- ea: `0x1fb0`
- end: `0x1fbb`
- name: `ImageComponentType::get_RdlType`
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
0x1fb0  ldtoken  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Image
0x1fb5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fba  ret
```
