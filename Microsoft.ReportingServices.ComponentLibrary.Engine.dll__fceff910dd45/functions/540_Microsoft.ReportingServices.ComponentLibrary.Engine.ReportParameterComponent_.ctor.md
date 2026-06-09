# Microsoft.ReportingServices.ComponentLibrary.Engine.ReportParameterComponent::.ctor

- ea: `0x540`
- end: `0x54d`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ReportParameterComponent::.ctor`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x690`

## callees

- `0x80`
- `0xa50`

## pseudocode

```c

```

## disassembly

```asm
0x540  ldarg.0
0x541  ldarg.1
0x542  call     class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType::get_ReportParameter()
0x547  call     instance void Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::.ctor(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject rdlObject, class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType type)
0x54c  ret
```
