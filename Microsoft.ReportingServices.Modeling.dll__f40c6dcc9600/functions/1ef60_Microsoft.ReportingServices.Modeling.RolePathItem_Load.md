# Microsoft.ReportingServices.Modeling.RolePathItem::Load

- ea: `0x1ef60`
- end: `0x1ef6d`
- name: `Microsoft.ReportingServices.Modeling.RolePathItem::Load`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xab10`

## string_xrefs

- `0x1ef61`: `RolePathItem`

## pseudocode

```c

```

## disassembly

```asm
0x1ef60  ldarg.1
0x1ef61  ldstr    aRolepathitem// "RolePathItem"
0x1ef66  ldarg.0
0x1ef67  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlReader::LoadObject(string elementName, class Microsoft.ReportingServices.Modeling.IXmlLoadable obj)
0x1ef6c  ret
```
