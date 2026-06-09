# Microsoft.SharePoint.Publishing.ImageRenditionValueTypeConverter::InitFromXml

- ea: `0x4d20`
- end: `0x4e2f`
- name: `Microsoft.SharePoint.Publishing.ImageRenditionValueTypeConverter::InitFromXml`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4d20`

## pseudocode

```c

```

## disassembly

```asm
0x4d20  ldarg.0
0x4d21  ldarg.1
0x4d22  ldarg.2
0x4d23  ldarg.3
0x4d24  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d29  starg.s  1
0x4d2b  ldarg.1
0x4d2c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition
0x4d31  stloc.0
0x4d32  ldloc.0
0x4d33  brfalse  loc_4E2D
0x4d38  ldarg.2
0x4d39  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x4d3e  stloc.s  4
0x4d40  br       loc_4E0A
0x4d45  ldloc.s  4
0x4d47  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4d4c  castclass [System.Xml]System.Xml.XmlNode
0x4d51  stloc.1
0x4d52  ldloc.1
0x4d53  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4d58  ldstr    aName// "Name"
0x4d5d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4d62  stloc.2
0x4d63  ldloc.2
0x4d64  brfalse  loc_4E0A
0x4d69  ldloc.2
0x4d6a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4d6f  stloc.3
0x4d70  ldloc.3
0x4d71  dup
0x4d72  stloc.s  5
0x4d74  brfalse  loc_4E0A
0x4d79  ldloc.s  5
0x4d7b  ldstr    aGroup// "Group"
0x4d80  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4d85  brtrue.s loc_4DC1
0x4d87  ldloc.s  5
0x4d89  ldstr    aHeight// "Height"
0x4d8e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4d93  brtrue.s loc_4DD0
0x4d95  ldloc.s  5
0x4d97  ldstr    aIdcsom// "IdCsom"
0x4d9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4da1  brtrue.s loc_4DDF
0x4da3  ldloc.s  5
0x4da5  ldstr    aName// "Name"
0x4daa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4daf  brtrue.s loc_4DEE
0x4db1  ldloc.s  5
0x4db3  ldstr    aWidth// "Width"
0x4db8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4dbd  brtrue.s loc_4DFD
0x4dbf  br.s     loc_4E0A
0x4dc1  ldloc.0
0x4dc2  ldloc.1
0x4dc3  ldarg.3
0x4dc4  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4dc9  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::set_Group(string)
0x4dce  br.s     loc_4E0A
0x4dd0  ldloc.0
0x4dd1  ldloc.1
0x4dd2  ldarg.3
0x4dd3  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4dd8  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::set_Height(int32)
0x4ddd  br.s     loc_4E0A
0x4ddf  ldloc.0
0x4de0  ldloc.1
0x4de1  ldarg.3
0x4de2  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4de7  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::set_IdCsom(int32)
0x4dec  br.s     loc_4E0A
0x4dee  ldloc.0
0x4def  ldloc.1
0x4df0  ldarg.3
0x4df1  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4df6  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::set_Name(string)
0x4dfb  br.s     loc_4E0A
0x4dfd  ldloc.0
0x4dfe  ldloc.1
0x4dff  ldarg.3
0x4e00  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4e05  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.ImageRendition::set_Width(int32)
0x4e0a  ldloc.s  4
0x4e0c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4e11  brtrue   loc_4D45
0x4e16  leave.s  loc_4E2D
0x4e18  ldloc.s  4
0x4e1a  isinst   [mscorlib]System.IDisposable
0x4e1f  stloc.s  6
0x4e21  ldloc.s  6
0x4e23  brfalse.s loc_4E2C
0x4e25  ldloc.s  6
0x4e27  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e2c  endfinally
0x4e2d  ldloc.0
0x4e2e  ret
```
