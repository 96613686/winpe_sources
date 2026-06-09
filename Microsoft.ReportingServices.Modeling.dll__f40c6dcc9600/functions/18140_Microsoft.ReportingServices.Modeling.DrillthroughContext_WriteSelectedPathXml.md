# Microsoft.ReportingServices.Modeling.DrillthroughContext::WriteSelectedPathXml

- ea: `0x18140`
- end: `0x18180`
- name: `Microsoft.ReportingServices.Modeling.DrillthroughContext::WriteSelectedPathXml`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x35fd0`

## callees

- `0xa5b0`
- `0xb340`
- `0xb3a0`
- `0xb480`
- `0xb4a0`
- `0x18140`
- `0x1e1f0`

## string_xrefs

- `0x18156`: `SelectedPath`
- `0x1816a`: `SelectedPath`

## pseudocode

```c

```

## disassembly

```asm
0x18140  ldarg.0
0x18141  call     class Microsoft.ReportingServices.Modeling.SemanticModelingSchema Microsoft.ReportingServices.Modeling.SemanticModelingSchema::get_Relaxed()
0x18146  ldc.i4.0
0x18147  newobj   instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::.ctor(class [System.Xml]System.Xml.XmlWriter xw, class Microsoft.ReportingServices.Modeling.ModelingXmlSchema schema, valuetype Microsoft.ReportingServices.Modeling.ModelingSerializationOptions options)
0x1814c  stloc.0
0x1814d  ldarg.1
0x1814e  callvirt instance bool class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.PathItem>::get_IsEmpty()
0x18153  brfalse.s loc_18168
0x18155  ldloc.0
0x18156  ldstr    aSelectedpath// "SelectedPath"
0x1815b  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteStartElement(string name)
0x18160  ldloc.0
0x18161  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteEndElement()
0x18166  br.s     loc_18174
0x18168  ldarg.1
0x18169  ldloc.0
0x1816a  ldstr    aSelectedpath// "SelectedPath"
0x1816f  callvirt instance void Microsoft.ReportingServices.Modeling.ExpressionPath::WriteTo(class Microsoft.ReportingServices.Modeling.ModelingXmlWriter xw, string pathElementName)
0x18174  ldloc.0
0x18175  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Modeling.ModelingXmlWriter::get_Writer()
0x1817a  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x1817f  ret
```
