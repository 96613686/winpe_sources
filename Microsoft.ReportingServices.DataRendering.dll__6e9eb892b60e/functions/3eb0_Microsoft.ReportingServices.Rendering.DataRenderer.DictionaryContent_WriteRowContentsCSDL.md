# Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::WriteRowContentsCSDL

- ea: `0x3eb0`
- end: `0x3f89`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::WriteRowContentsCSDL`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x37f0`

## callees

- `0x3eb0`
- `0x3fa0`

## string_xrefs

- `0x3f11`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/feedmetadata`
- `0x3f2c`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/feedmetadata`
- `0x3f5e`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/feedmetadata`

## pseudocode

```c

```

## disassembly

```asm
0x3eb0  ldarg.3
0x3eb1  ldarg.s  4
0x3eb3  add
0x3eb4  stloc.0
0x3eb5  ldc.i4.0
0x3eb6  stloc.1
0x3eb7  br       loc_3F77
0x3ebc  ldarg.0
0x3ebd  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueNames
0x3ec2  ldloc.1
0x3ec3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x3ec8  ldarg.0
0x3ec9  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueTypes
0x3ece  ldloc.1
0x3ecf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x3ed4  stloc.2
0x3ed5  ldloc.2
0x3ed6  brtrue.s loc_3EDE
0x3ed8  ldstr    aEdmString// "Edm.String"
0x3edd  stloc.2
0x3ede  call     string [System.Xml]System.Xml.XmlConvert::EncodeLocalName(string)
0x3ee3  stloc.3
0x3ee4  ldarg.1
0x3ee5  ldstr    aProperty// "Property"
0x3eea  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3eef  ldarg.1
0x3ef0  ldstr    aName// "Name"
0x3ef5  ldloc.3
0x3ef6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3efb  ldarg.1
0x3efc  ldstr    aType// "Type"
0x3f01  ldloc.2
0x3f02  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3f07  ldloc.1
0x3f08  ldarg.3
0x3f09  bge.s    loc_3F22
0x3f0b  ldarg.1
0x3f0c  ldstr    aIsparameter// "IsParameter"
0x3f11  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0x3f16  ldstr    aTrue// "true"
0x3f1b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string)
0x3f20  br.s     loc_3F6D
0x3f22  ldloc.1
0x3f23  ldloc.0
0x3f24  bge.s    loc_3F3D
0x3f26  ldarg.1
0x3f27  ldstr    aIscontext// "IsContext"
0x3f2c  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0x3f31  ldstr    aTrue// "true"
0x3f36  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string)
0x3f3b  br.s     loc_3F6D
0x3f3d  ldarg.2
0x3f3e  ldloc.1
0x3f3f  ldarg.3
0x3f40  sub
0x3f41  ldc.i4.1
0x3f42  add
0x3f43  ldloca.s 4
0x3f45  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata>::TryGetValue(var<u1>, !!T0)
0x3f4a  pop
0x3f4b  ldloc.s  4
0x3f4d  brfalse.s loc_3F6D
0x3f4f  ldloc.s  4
0x3f51  callvirt instance bool Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata::get_IsDynamic()
0x3f56  brfalse.s loc_3F6D
0x3f58  ldarg.1
0x3f59  ldstr    aIsgroup// "IsGroup"
0x3f5e  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/sqlserver/"...
0x3f63  ldstr    aTrue// "true"
0x3f68  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string)
0x3f6d  ldarg.1
0x3f6e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x3f73  ldloc.1
0x3f74  ldc.i4.1
0x3f75  add
0x3f76  stloc.1
0x3f77  ldloc.1
0x3f78  ldarg.0
0x3f79  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueNames
0x3f7e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x3f83  blt      loc_3EBC
0x3f88  ret
```
