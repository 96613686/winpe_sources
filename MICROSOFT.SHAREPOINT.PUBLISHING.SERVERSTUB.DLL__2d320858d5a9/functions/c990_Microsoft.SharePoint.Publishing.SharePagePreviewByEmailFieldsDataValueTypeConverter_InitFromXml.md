# Microsoft.SharePoint.Publishing.SharePagePreviewByEmailFieldsDataValueTypeConverter::InitFromXml

- ea: `0xc990`
- end: `0xca3c`
- name: `Microsoft.SharePoint.Publishing.SharePagePreviewByEmailFieldsDataValueTypeConverter::InitFromXml`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xc990`

## pseudocode

```c

```

## disassembly

```asm
0xc990  ldarg.0
0xc991  ldarg.1
0xc992  ldarg.2
0xc993  ldarg.3
0xc994  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xc999  starg.s  1
0xc99b  ldarg.1
0xc99c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePagePreviewByEmailFieldsData
0xc9a1  stloc.0
0xc9a2  ldloc.0
0xc9a3  brfalse  loc_CA3A
0xc9a8  ldarg.2
0xc9a9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0xc9ae  stloc.s  4
0xc9b0  br.s     loc_CA1A
0xc9b2  ldloc.s  4
0xc9b4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc9b9  castclass [System.Xml]System.Xml.XmlNode
0xc9be  stloc.1
0xc9bf  ldloc.1
0xc9c0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc9c5  ldstr    aName// "Name"
0xc9ca  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc9cf  stloc.2
0xc9d0  ldloc.2
0xc9d1  brfalse.s loc_CA1A
0xc9d3  ldloc.2
0xc9d4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc9d9  stloc.3
0xc9da  ldloc.3
0xc9db  dup
0xc9dc  stloc.s  5
0xc9de  brfalse.s loc_CA1A
0xc9e0  ldloc.s  5
0xc9e2  ldstr    aMessage// "message"
0xc9e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc9ec  brtrue.s loc_C9FE
0xc9ee  ldloc.s  5
0xc9f0  ldstr    aRecipientemail// "recipientEmails"
0xc9f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc9fa  brtrue.s loc_CA0D
0xc9fc  br.s     loc_CA1A
0xc9fe  ldloc.0
0xc9ff  ldloc.1
0xca00  ldarg.3
0xca01  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xca06  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePagePreviewByEmailFieldsData::set_Message(string)
0xca0b  br.s     loc_CA1A
0xca0d  ldloc.0
0xca0e  ldloc.1
0xca0f  ldarg.3
0xca10  call     string[] [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToStringArray(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xca15  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePagePreviewByEmailFieldsData::set_RecipientEmails(string[])
0xca1a  ldloc.s  4
0xca1c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xca21  brtrue.s loc_C9B2
0xca23  leave.s  loc_CA3A
0xca25  ldloc.s  4
0xca27  isinst   [mscorlib]System.IDisposable
0xca2c  stloc.s  6
0xca2e  ldloc.s  6
0xca30  brfalse.s loc_CA39
0xca32  ldloc.s  6
0xca34  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xca39  endfinally
0xca3a  ldloc.0
0xca3b  ret
```
