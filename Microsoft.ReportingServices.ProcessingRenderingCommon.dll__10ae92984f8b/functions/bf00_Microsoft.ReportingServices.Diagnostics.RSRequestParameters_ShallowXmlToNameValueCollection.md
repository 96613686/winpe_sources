# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ShallowXmlToNameValueCollection

- ea: `0xbf00`
- end: `0xbfa0`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::ShallowXmlToNameValueCollection`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc1d0`
- `0xc3f0`

## callees

- `0x4950`
- `0x4c70`
- `0xbf00`

## pseudocode

```c

```

## disassembly

```asm
0xbf00  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0xbf05  stloc.0
0xbf06  ldarg.0
0xbf07  brfalse.s loc_BF16
0xbf09  ldarg.0
0xbf0a  ldsfld   string [mscorlib]System.String::Empty
0xbf0f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf14  brfalse.s loc_BF18
0xbf16  ldloc.0
0xbf17  ret
0xbf18  ldarg.0
0xbf19  call     class [System.Xml]System.Xml.XmlTextReader Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeCreateXmlTextReader(string xmlContent)
0xbf1e  stloc.1
0xbf1f  ldloc.1
0xbf20  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xbf25  pop
0xbf26  ldloc.1
0xbf27  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xbf2c  ldc.i4.1
0xbf2d  bne.un.s loc_BF3E
0xbf2f  ldloc.1
0xbf30  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xbf35  ldarg.1
0xbf36  ldc.i4.4
0xbf37  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xbf3c  brfalse.s loc_BF8E
0xbf3e  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xbf43  throw
0xbf44  ldloc.1
0xbf45  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0xbf4a  brfalse.s loc_BF8E
0xbf4c  ldloc.1
0xbf4d  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xbf52  ldloc.1
0xbf53  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xbf58  stloc.2
0xbf59  ldloc.2
0xbf5a  call     string Microsoft.ReportingServices.Diagnostics.XmlUtil::DecodePropertyName(string name)
0xbf5f  stloc.2
0xbf60  ldloc.1
0xbf61  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0xbf66  stloc.3
0xbf67  ldloc.0
0xbf68  ldloc.2
0xbf69  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::GetValues(string)
0xbf6e  brfalse.s loc_BF76
0xbf70  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xbf75  throw
0xbf76  ldloc.0
0xbf77  ldloc.2
0xbf78  ldloc.3
0xbf79  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0xbf7e  brtrue.s loc_BF8E
0xbf80  ldloc.1
0xbf81  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0xbf86  brfalse.s loc_BF8E
0xbf88  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0xbf8d  throw
0xbf8e  ldloc.1
0xbf8f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xbf94  brtrue.s loc_BF44
0xbf96  leave.s  loc_BF9E
0xbf98  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MalformedXmlException::.ctor(class [System.Xml]System.Xml.XmlException)
0xbf9d  throw
0xbf9e  ldloc.0
0xbf9f  ret
```
