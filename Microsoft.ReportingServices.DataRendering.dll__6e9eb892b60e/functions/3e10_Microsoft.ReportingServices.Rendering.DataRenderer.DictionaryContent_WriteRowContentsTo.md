# Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::WriteRowContentsTo

- ea: `0x3e10`
- end: `0x3ea2`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::WriteRowContentsTo`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3de0`

## callees

- `0x3e10`
- `0xa460`

## string_xrefs

- `0x3e42`: `http://schemas.microsoft.com/ado/2007/08/dataservices`
- `0x3e55`: `http://schemas.microsoft.com/ado/2007/08/dataservices/metadata`
- `0x3e69`: `http://schemas.microsoft.com/ado/2007/08/dataservices/metadata`

## pseudocode

```c

```

## disassembly

```asm
0x3e10  ldc.i4.0
0x3e11  stloc.0
0x3e12  br.s     loc_3E90
0x3e14  ldarg.0
0x3e15  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueNames
0x3e1a  ldloc.0
0x3e1b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x3e20  ldarg.0
0x3e21  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueTypes
0x3e26  ldloc.0
0x3e27  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x3e2c  stloc.1
0x3e2d  ldarg.0
0x3e2e  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueContents
0x3e33  ldloc.0
0x3e34  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x3e39  stloc.2
0x3e3a  call     string [System.Xml]System.Xml.XmlConvert::EncodeLocalName(string)
0x3e3f  stloc.3
0x3e40  ldarg.1
0x3e41  ldloc.3
0x3e42  ldstr    aHttpSchemasMic_4// "http://schemas.microsoft.com/ado/2007/0"...
0x3e47  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x3e4c  ldloc.1
0x3e4d  brfalse.s loc_3E60
0x3e4f  ldarg.1
0x3e50  ldstr    aType_0// "type"
0x3e55  ldstr    aHttpSchemasMic_5// "http://schemas.microsoft.com/ado/2007/0"...
0x3e5a  ldloc.1
0x3e5b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string)
0x3e60  ldloc.2
0x3e61  brtrue.s loc_3E7A
0x3e63  ldarg.1
0x3e64  ldstr    aNull// "null"
0x3e69  ldstr    aHttpSchemasMic_5// "http://schemas.microsoft.com/ado/2007/0"...
0x3e6e  ldstr    aTrue// "true"
0x3e73  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string)
0x3e78  br.s     loc_3E86
0x3e7a  ldarg.1
0x3e7b  ldloc.2
0x3e7c  call     string Microsoft.ReportingServices.Rendering.DataRenderer.XmlVisitorBase::FilterInvalidXMLCharacters(string value)
0x3e81  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x3e86  ldarg.1
0x3e87  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x3e8c  ldloc.0
0x3e8d  ldc.i4.1
0x3e8e  add
0x3e8f  stloc.0
0x3e90  ldloc.0
0x3e91  ldarg.0
0x3e92  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueNames
0x3e97  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x3e9c  blt      loc_3E14
0x3ea1  ret
```
