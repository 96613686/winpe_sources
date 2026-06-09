# Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessQuery

- ea: `0xb2e0`
- end: `0xb3bf`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessQuery`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0xb1d0`

## callees

- `0x2920`
- `0x9430`
- `0x9770`
- `0xa750`
- `0xb2e0`
- `0xb3c0`
- `0xbc60`
- `0xc730`
- `0xc7e0`
- `0xc810`
- `0x13410`
- `0x134b0`
- `0x17f80`

## string_xrefs

- `0xb2e1`: `ObjectPathId`

## pseudocode

```c

```

## disassembly

```asm
0xb2e0  ldarg.1
0xb2e1  ldstr    aObjectpathid// "ObjectPathId"
0xb2e6  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xb2eb  stloc.0
0xb2ec  ldarg.0
0xb2ed  ldloc.0
0xb2ee  call     instance object Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectFromObjectPathId(string objectPathId)
0xb2f3  stloc.1
0xb2f4  ldarg.1
0xb2f5  ldstr    aId// "Id"
0xb2fa  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xb2ff  stloc.2
0xb300  ldloc.2
0xb301  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb306  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0xb30b  stloc.3
0xb30c  ldloc.1
0xb30d  brtrue.s loc_B327
0xb30f  ldarg.0
0xb310  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb315  ldloc.3
0xb316  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int64 value)
0xb31b  ldarg.0
0xb31c  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb321  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xb326  ret
0xb327  ldarg.1
0xb328  ldstr    aCqQuery// "cq:Query"
0xb32d  call     class [System.Xml]System.Xml.XmlNamespaceManager Microsoft.SharePoint.Client.ClientMethodsProcessor::get_NamespaceManager()
0xb332  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xb337  castclass [System.Xml]System.Xml.XmlElement
0xb33c  stloc.s  4
0xb33e  ldloc.s  4
0xb340  newobj   instance void Microsoft.SharePoint.Client.ClientQuery::.ctor(class [System.Xml]System.Xml.XmlElement xeQuery)
0xb345  stloc.s  5
0xb347  ldnull
0xb348  stloc.s  6
0xb34a  ldarg.1
0xb34b  ldstr    aCqChilditemque// "cq:ChildItemQuery"
0xb350  call     class [System.Xml]System.Xml.XmlNamespaceManager Microsoft.SharePoint.Client.ClientMethodsProcessor::get_NamespaceManager()
0xb355  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xb35a  castclass [System.Xml]System.Xml.XmlElement
0xb35f  stloc.s  7
0xb361  ldloc.s  7
0xb363  brfalse.s loc_B36E
0xb365  ldloc.s  7
0xb367  newobj   instance void Microsoft.SharePoint.Client.ClientQuery::.ctor(class [System.Xml]System.Xml.XmlElement xeQuery)
0xb36c  stloc.s  6
0xb36e  ldarg.0
0xb36f  ldloc.1
0xb370  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb375  call     instance class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ClientMethodsProcessor::GetServerStub(class [mscorlib]System.Type type)
0xb37a  stloc.s  8
0xb37c  ldloc.s  8
0xb37e  ldloc.1
0xb37f  ldloc.s  5
0xb381  ldloc.s  6
0xb383  callvirt instance void Microsoft.SharePoint.Client.ServerStub::OnQuerying(object obj, class Microsoft.SharePoint.Client.ClientQuery query, class Microsoft.SharePoint.Client.ClientQuery childItemQuery)
0xb388  ldarg.0
0xb389  call     instance class WriterSnapshot Microsoft.SharePoint.Client.ClientMethodsProcessor::TakeWriterSnapshot()
0xb38e  stloc.s  9
0xb390  ldarg.0
0xb391  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb396  ldloc.3
0xb397  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int64 value)
0xb39c  ldc.i4.0
0xb39d  ldloc.s  5
0xb39f  ldloc.s  6
0xb3a1  newobj   instance void Microsoft.SharePoint.Client.ClientObjectQuery::.ctor(bool selectAll, class Microsoft.SharePoint.Client.ClientQuery query, class Microsoft.SharePoint.Client.ClientQuery childItemQuery)
0xb3a6  stloc.s  0xA
0xb3a8  ldarg.0
0xb3a9  ldloc.1
0xb3aa  ldloc.s  0xA
0xb3ac  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::WriteQueryResults(object obj, class Microsoft.SharePoint.Client.ClientObjectQuery objQuery)
0xb3b1  leave.s  loc_B3BE
0xb3b3  pop
0xb3b4  ldarg.0
0xb3b5  ldloc.s  9
0xb3b7  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::RestoreWriterSnapshot(class WriterSnapshot snapshot)
0xb3bc  rethrow
0xb3be  ret
```
