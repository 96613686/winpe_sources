# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Metadata

- ea: `0x1a0`
- end: `0x1ac`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Metadata`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1a0  ldarg.0
0x1a1  call     instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_RdlObject()
0x1a6  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::get_ComponentMetadata()
0x1ab  ret
```
