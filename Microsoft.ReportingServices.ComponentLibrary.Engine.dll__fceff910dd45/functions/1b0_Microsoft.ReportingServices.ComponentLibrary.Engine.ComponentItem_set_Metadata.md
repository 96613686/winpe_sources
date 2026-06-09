# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_Metadata

- ea: `0x1b0`
- end: `0x1bd`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::set_Metadata`
- size: `13`
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
0x1b0  ldarg.0
0x1b1  call     instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_RdlObject()
0x1b6  ldarg.1
0x1b7  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject::set_ComponentMetadata(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ComponentMetadata)
0x1bc  ret
```
