# Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessInstantiateObjectPath

- ea: `0xb6e0`
- end: `0xb767`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessInstantiateObjectPath`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xb1d0`

## callees

- `0xb6e0`
- `0xbc60`
- `0xc7e0`
- `0xc810`
- `0x13030`
- `0x13220`
- `0x132d0`
- `0x13420`
- `0x134b0`
- `0x17f80`

## string_xrefs

- `0xb6f9`: `ObjectPathId`

## pseudocode

```c

```

## disassembly

```asm
0xb6e0  ldarg.1
0xb6e1  ldstr    aId// "Id"
0xb6e6  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xb6eb  stloc.0
0xb6ec  ldloc.0
0xb6ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb6f2  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0xb6f7  stloc.1
0xb6f8  ldarg.1
0xb6f9  ldstr    aObjectpathid// "ObjectPathId"
0xb6fe  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xb703  stloc.2
0xb704  ldarg.0
0xb705  ldloc.2
0xb706  call     instance object Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectFromObjectPathId(string objectPathId)
0xb70b  stloc.3
0xb70c  ldloc.3
0xb70d  ldnull
0xb70e  ceq
0xb710  stloc.s  4
0xb712  ldarg.0
0xb713  call     instance class WriterSnapshot Microsoft.SharePoint.Client.ClientMethodsProcessor::TakeWriterSnapshot()
0xb718  stloc.s  5
0xb71a  ldarg.0
0xb71b  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb720  ldloc.1
0xb721  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int64 value)
0xb726  ldarg.0
0xb727  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb72c  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0xb731  ldarg.0
0xb732  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb737  ldstr    aIsnull// "IsNull"
0xb73c  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0xb741  ldarg.0
0xb742  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb747  ldloc.s  4
0xb749  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(bool value)
0xb74e  ldarg.0
0xb74f  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb754  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0xb759  leave.s  loc_B766
0xb75b  pop
0xb75c  ldarg.0
0xb75d  ldloc.s  5
0xb75f  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::RestoreWriterSnapshot(class WriterSnapshot snapshot)
0xb764  rethrow
0xb766  ret
```
