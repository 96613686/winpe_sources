# Microsoft.ReportingServices.Modeling.DataSourceView::WriteTo

- ea: `0xd1f0`
- end: `0xd29c`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::WriteTo`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x17040`

## callees

- `0xd1f0`
- `0xd2a0`

## string_xrefs

- `0xd204`: `http://schemas.microsoft.com/analysisservices/2003/engine`
- `0xd242`: `CreatedTimestamp`
- `0xd253`: `LastSchemaUpdate`

## pseudocode

```c

```

## disassembly

```asm
0xd1f0  ldarg.1
0xd1f1  brtrue.s loc_D1FE
0xd1f3  ldstr    aXw// "xw"
0xd1f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd1fd  throw
0xd1fe  ldarg.1
0xd1ff  ldstr    aDatasourceview// "DataSourceView"
0xd204  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/analysisse"...
0xd209  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xd20e  ldarg.1
0xd20f  ldstr    aId// "ID"
0xd214  ldarg.0
0xd215  ldfld    string Microsoft.ReportingServices.Modeling.DataSourceView::m_id
0xd21a  call     T0x2B000032
0xd21f  ldarg.1
0xd220  ldstr    aName// "Name"
0xd225  ldarg.0
0xd226  ldfld    string Microsoft.ReportingServices.Modeling.DataSourceView::m_name
0xd22b  call     T0x2B000032
0xd230  ldarg.1
0xd231  ldstr    aDescription// "Description"
0xd236  ldarg.0
0xd237  ldfld    string Microsoft.ReportingServices.Modeling.DataSourceView::m_description
0xd23c  call     T0x2B000032
0xd241  ldarg.1
0xd242  ldstr    aCreatedtimesta// "CreatedTimestamp"
0xd247  ldarg.0
0xd248  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Modeling.DataSourceView::m_createdTimestamp
0xd24d  call     T0x2B000033
0xd252  ldarg.1
0xd253  ldstr    aLastschemaupda// "LastSchemaUpdate"
0xd258  ldarg.0
0xd259  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Modeling.DataSourceView::m_lastSchemaUpdate
0xd25e  call     T0x2B000033
0xd263  ldarg.0
0xd264  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.ReportingServices.Modeling.DataSourceView::m_annotations
0xd269  brfalse.s loc_D277
0xd26b  ldarg.0
0xd26c  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.ReportingServices.Modeling.DataSourceView::m_annotations
0xd271  ldarg.1
0xd272  callvirt instance void [System.Xml]System.Xml.XmlNode::WriteTo(class [System.Xml]System.Xml.XmlWriter)
0xd277  ldarg.1
0xd278  ldstr    aDatasourceid// "DataSourceID"
0xd27d  ldarg.0
0xd27e  ldfld    string Microsoft.ReportingServices.Modeling.DataSourceView::m_dataSourceID
0xd283  call     T0x2B000032
0xd288  ldarg.0
0xd289  ldarg.1
0xd28a  call     instance void Microsoft.ReportingServices.Modeling.DataSourceView::WriteSchema(class [System.Xml]System.Xml.XmlWriter xw)
0xd28f  ldarg.1
0xd290  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xd295  ldarg.1
0xd296  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0xd29b  ret
```
