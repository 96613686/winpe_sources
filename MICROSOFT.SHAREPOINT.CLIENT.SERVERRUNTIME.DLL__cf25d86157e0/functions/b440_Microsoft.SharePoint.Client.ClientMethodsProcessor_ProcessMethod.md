# Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessMethod

- ea: `0xb440`
- end: `0xb550`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::ProcessMethod`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0xb1d0`

## callees

- `0xa750`
- `0xb440`
- `0xbc60`
- `0xc260`
- `0xc410`
- `0xc5f0`
- `0xc650`
- `0xc7e0`
- `0xc810`
- `0x11ee0`
- `0x13410`
- `0x134b0`
- `0x17f80`

## string_xrefs

- `0xb44d`: `ObjectPathId`

## pseudocode

```c

```

## disassembly

```asm
0xb440  ldarg.1
0xb441  ldstr    aName// "Name"
0xb446  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xb44b  stloc.0
0xb44c  ldarg.1
0xb44d  ldstr    aObjectpathid// "ObjectPathId"
0xb452  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xb457  stloc.1
0xb458  ldarg.0
0xb459  ldloc.1
0xb45a  call     instance object Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectFromObjectPathId(string objectPathId)
0xb45f  stloc.2
0xb460  ldloc.2
0xb461  brtrue.s loc_B470
0xb463  ldarg.0
0xb464  ldarg.0
0xb465  ldloc.1
0xb466  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetObjectStackTrace(string objectPathId)
0xb46b  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::ThrowNullReference(string objectStackTrace)
0xb470  ldarg.1
0xb471  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb476  ldstr    aVersion_0// "Version"
0xb47b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb480  brfalse.s loc_B4A0
0xb482  ldarg.0
0xb483  ldloc.1
0xb484  ldloc.2
0xb485  ldloc.0
0xb486  ldarg.1
0xb487  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb48c  ldstr    aVersion_0// "Version"
0xb491  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb496  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb49b  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::CheckObjectVersionForMethod(string objectPathId, object obj, string methodName, string expectedObjectVersion)
0xb4a0  ldarg.1
0xb4a1  ldstr    aCqParameters// "cq:Parameters"
0xb4a6  call     class [System.Xml]System.Xml.XmlNamespaceManager Microsoft.SharePoint.Client.ClientMethodsProcessor::get_NamespaceManager()
0xb4ab  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xb4b0  castclass [System.Xml]System.Xml.XmlElement
0xb4b5  stloc.3
0xb4b6  ldarg.0
0xb4b7  ldloc.2
0xb4b8  ldloc.0
0xb4b9  ldloc.3
0xb4ba  brfalse.s loc_B4C4
0xb4bc  ldloc.3
0xb4bd  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0xb4c2  br.s     loc_B4C5
0xb4c4  ldnull
0xb4c5  ldloca.s 4
0xb4c7  call     instance object Microsoft.SharePoint.Client.ClientMethodsProcessor::InvokeMethod(object obj, string methodName, class [System.Xml]System.Xml.XmlNodeList xmlargs, [out] bool& isVoid)
0xb4cc  stloc.s  5
0xb4ce  ldarg.1
0xb4cf  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb4d4  ldstr    aId// "Id"
0xb4d9  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb4de  brfalse.s loc_B54F
0xb4e0  ldloc.s  4
0xb4e2  brtrue.s loc_B54F
0xb4e4  ldarg.1
0xb4e5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb4ea  ldstr    aId// "Id"
0xb4ef  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb4f4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb4f9  stloc.s  6
0xb4fb  ldloc.s  6
0xb4fd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb502  call     int64 [mscorlib]System.Int64::Parse(string, class [mscorlib]System.IFormatProvider)
0xb507  stloc.s  7
0xb509  ldarg.0
0xb50a  call     instance class WriterSnapshot Microsoft.SharePoint.Client.ClientMethodsProcessor::TakeWriterSnapshot()
0xb50f  stloc.s  8
0xb511  ldarg.0
0xb512  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb517  ldloc.s  7
0xb519  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int64 value)
0xb51e  ldloc.s  5
0xb520  brtrue.s loc_B52F
0xb522  ldarg.0
0xb523  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb528  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xb52d  br.s     loc_B542
0xb52f  ldarg.0
0xb530  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb535  ldloc.s  5
0xb537  ldarg.0
0xb538  ldfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientMethodsProcessor::m_proxyContext
0xb53d  call     void Microsoft.SharePoint.Client.DataConverter::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xb542  leave.s  loc_B54F
0xb544  pop
0xb545  ldarg.0
0xb546  ldloc.s  8
0xb548  call     instance void Microsoft.SharePoint.Client.ClientMethodsProcessor::RestoreWriterSnapshot(class WriterSnapshot snapshot)
0xb54d  rethrow
0xb54f  ret
```
