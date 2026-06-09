# Microsoft.ReportingServices.Modeling.DataSourceView::WriteSchema

- ea: `0xd2a0`
- end: `0xd2c3`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::WriteSchema`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1f0`

## callees

- `0x2f860`

## string_xrefs

- `0xd2a6`: `http://schemas.microsoft.com/analysisservices/2003/engine`

## pseudocode

```c

```

## disassembly

```asm
0xd2a0  ldarg.1
0xd2a1  ldstr    aSchema// "Schema"
0xd2a6  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/analysisse"...
0xd2ab  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xd2b0  ldarg.0
0xd2b1  ldfld    class IDsvInfo Microsoft.ReportingServices.Modeling.DataSourceView::m_dsvInfo
0xd2b6  ldarg.1
0xd2b7  callvirt instance void IDsvInfo::WriteTo(class [System.Xml]System.Xml.XmlWriter xw)
0xd2bc  ldarg.1
0xd2bd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xd2c2  ret
```
