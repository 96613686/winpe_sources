# Microsoft.ReportingServices.Modeling.DataSourceView::WriteElementIfNonDefault

- ea: `0xd2d0`
- end: `0xd329`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::WriteElementIfNonDefault`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xd2d0`

## string_xrefs

- `0xd30c`: `http://schemas.microsoft.com/analysisservices/2003/engine`

## pseudocode

```c

```

## disassembly

```asm
0xd2d0  ldarg.2
0xd2d1  box      mvar<u1>
0xd2d6  brfalse.s loc_D328
0xd2d8  ldarg.2
0xd2d9  box      mvar<u1>
0xd2de  ldloca.s 0
0xd2e0  initobj  mvar<u1>
0xd2e6  ldloc.0
0xd2e7  box      mvar<u1>
0xd2ec  call     bool [mscorlib]System.Object::Equals(object, object)
0xd2f1  brtrue.s loc_D328
0xd2f3  ldarg.2
0xd2f4  box      mvar<u1>
0xd2f9  isinst   [mscorlib]System.String
0xd2fe  ldsfld   string [mscorlib]System.String::Empty
0xd303  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xd308  brfalse.s loc_D328
0xd30a  ldarg.0
0xd30b  ldarg.1
0xd30c  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/analysisse"...
0xd311  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0xd316  ldarg.0
0xd317  ldarg.2
0xd318  box      mvar<u1>
0xd31d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(object)
0xd322  ldarg.0
0xd323  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xd328  ret
```
