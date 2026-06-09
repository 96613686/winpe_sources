# Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::WriteContentsTo

- ea: `0x3de0`
- end: `0x3e0c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::WriteContentsTo`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3de0`
- `0x3e10`

## string_xrefs

- `0x3df4`: `http://schemas.microsoft.com/ado/2007/08/dataservices/metadata`

## pseudocode

```c

```

## disassembly

```asm
0x3de0  ldc.i4.0
0x3de1  ldarg.0
0x3de2  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::m_valueNames
0x3de7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x3dec  bge.s    loc_3E0B
0x3dee  ldarg.1
0x3def  ldstr    aProperties// "properties"
0x3df4  ldstr    aHttpSchemasMic_5// "http://schemas.microsoft.com/ado/2007/0"...
0x3df9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string, string)
0x3dfe  ldarg.0
0x3dff  ldarg.1
0x3e00  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::WriteRowContentsTo(class [System.Xml]System.Xml.XmlWriter xmlWriter)
0x3e05  ldarg.1
0x3e06  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x3e0b  ret
```
