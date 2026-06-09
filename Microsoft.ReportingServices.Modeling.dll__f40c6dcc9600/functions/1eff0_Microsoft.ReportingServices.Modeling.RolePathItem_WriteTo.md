# Microsoft.ReportingServices.Modeling.RolePathItem::WriteTo

- ea: `0x1eff0`
- end: `0x1f013`
- name: `Microsoft.ReportingServices.Modeling.RolePathItem::WriteTo`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xb480`
- `0xb4a0`
- `0xb530`

## string_xrefs

- `0x1eff1`: `RolePathItem`

## pseudocode

```c

```

## disassembly

```asm
0x1eff0  ldarg.1
0x1eff1  ldstr    aRolepathitem// "RolePathItem"
0x1eff6  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteStartElement(string name)
0x1effb  ldarg.1
0x1effc  ldstr    aRoleid// "RoleID"
0x1f001  ldarg.0
0x1f002  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.RolePathItem::m_role
0x1f007  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteReferenceElement(string name, object item)
0x1f00c  ldarg.1
0x1f00d  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteEndElement()
0x1f012  ret
```
