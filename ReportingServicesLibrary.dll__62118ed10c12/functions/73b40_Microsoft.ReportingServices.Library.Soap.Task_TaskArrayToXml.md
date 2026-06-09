# Microsoft.ReportingServices.Library.Soap.Task::TaskArrayToXml

- ea: `0x73b40`
- end: `0x73ba1`
- name: `Microsoft.ReportingServices.Library.Soap.Task::TaskArrayToXml`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3cfd0`
- `0x3d5b0`

## callees

- `0x73b40`

## string_xrefs

- `0x73b58`: `Tasks`
- `0x73b77`: `TaskID`

## pseudocode

```c

```

## disassembly

```asm
0x73b40  ldarg.0
0x73b41  brtrue.s loc_73B45
0x73b43  ldnull
0x73b44  ret
0x73b45  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::get_CatalogCulture()
0x73b4a  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x73b4f  stloc.0
0x73b50  ldloc.0
0x73b51  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x73b56  stloc.1
0x73b57  ldloc.1
0x73b58  ldstr    aTasks// "Tasks"
0x73b5d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x73b62  ldc.i4.0
0x73b63  stloc.2
0x73b64  br.s     loc_73B8E
0x73b66  ldloc.1
0x73b67  ldstr    aTask// "Task"
0x73b6c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x73b71  ldarg.0
0x73b72  ldloc.2
0x73b73  ldelem.ref
0x73b74  brfalse.s loc_73B84
0x73b76  ldloc.1
0x73b77  ldstr    aTaskid// "TaskID"
0x73b7c  ldarg.0
0x73b7d  ldloc.2
0x73b7e  ldelem.ref
0x73b7f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x73b84  ldloc.1
0x73b85  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x73b8a  ldloc.2
0x73b8b  ldc.i4.1
0x73b8c  add
0x73b8d  stloc.2
0x73b8e  ldloc.2
0x73b8f  ldarg.0
0x73b90  ldlen
0x73b91  conv.i4
0x73b92  blt.s    loc_73B66
0x73b94  ldloc.1
0x73b95  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x73b9a  ldloc.0
0x73b9b  callvirt instance string [mscorlib]System.Object::ToString()
0x73ba0  ret
```
