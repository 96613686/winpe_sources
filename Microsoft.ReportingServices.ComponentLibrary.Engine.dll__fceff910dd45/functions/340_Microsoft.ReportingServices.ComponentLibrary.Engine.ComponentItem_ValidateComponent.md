# Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::ValidateComponent

- ea: `0x340`
- end: `0x34f`
- name: `Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::ValidateComponent`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x580`

## callees

- `0x160`
- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldarg.0
0x341  call     instance class Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentType Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_Type()
0x346  pop
0x347  ldarg.0
0x348  call     instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportObject Microsoft.ReportingServices.ComponentLibrary.Engine.ComponentItem::get_RdlObject()
0x34d  pop
0x34e  ret
```
