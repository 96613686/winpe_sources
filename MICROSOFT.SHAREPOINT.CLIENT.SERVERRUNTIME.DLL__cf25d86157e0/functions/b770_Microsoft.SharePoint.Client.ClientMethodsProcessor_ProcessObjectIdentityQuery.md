# Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessObjectIdentityQuery

- ea: `0xb770`
- end: `0xb815`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessObjectIdentityQuery`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0xb1d0`

## callees

- `0xb770`
- `0xbc60`
- `0xc580`
- `0xc7e0`
- `0xc810`
- `0x13030`
- `0x13220`
- `0x132d0`
- `0x13410`
- `0x134b0`
- `0x13720`
- `0x17f80`

## string_xrefs

- `0xb771`: `ObjectPathId`

## pseudocode

```c

```

## disassembly

```asm
0xb770  ldarg.1
0xb771  ldstr    aObjectpathid// "ObjectPathId"
0xb776  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xb77b  stloc.0
0xb77c  ldarg.0
0xb77d  ldloc.0
0xb77e  call     instance object Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectFromObjectPathId(string objectPathId)
0xb783  stloc.1
0xb784  ldarg.1
0xb785  ldstr    aId// "Id"
0xb78a  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xb78f  stloc.2
0xb790  ldloc.2
0xb791  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb796  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0xb79b  stloc.3
0xb79c  ldloc.1
0xb79d  brtrue.s loc_B7B7
0xb79f  ldarg.0
0xb7a0  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb7a5  ldloc.3
0xb7a6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int64 value)
0xb7ab  ldarg.0
0xb7ac  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb7b1  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xb7b6  ret
0xb7b7  ldarg.0
0xb7b8  ldloc.1
0xb7b9  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectIdentity(object value)
0xb7be  stloc.s  4
0xb7c0  ldarg.0
0xb7c1  call     instance class WriterSnapshot Microsoft.SharePoint.Client.ClientMethodsProcessor::TakeWriterSnapshot()
0xb7c6  stloc.s  5
0xb7c8  ldarg.0
0xb7c9  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb7ce  ldloc.3
0xb7cf  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int64 value)
0xb7d4  ldarg.0
0xb7d5  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb7da  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartObjectScope()
0xb7df  ldarg.0
0xb7e0  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb7e5  ldstr    aObjectidentity// "_ObjectIdentity_"
0xb7ea  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteName(string name)
0xb7ef  ldarg.0
0xb7f0  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb7f5  ldloc.s  4
0xb7f7  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0xb7fc  ldarg.0
0xb7fd  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb802  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0xb807  leave.s  loc_B814
0xb809  pop
0xb80a  ldarg.0
0xb80b  ldloc.s  5
0xb80d  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::RestoreWriterSnapshot(class WriterSnapshot snapshot)
0xb812  rethrow
0xb814  ret
```
