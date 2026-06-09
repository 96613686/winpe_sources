# Microsoft.SharePoint.Publishing.PublishingPageInformationCsomValueTypeConverter::InitFromXml

- ea: `0xb240`
- end: `0xb30f`
- name: `Microsoft.SharePoint.Publishing.PublishingPageInformationCsomValueTypeConverter::InitFromXml`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xb240`

## pseudocode

```c

```

## disassembly

```asm
0xb240  ldarg.0
0xb241  ldarg.1
0xb242  ldarg.2
0xb243  ldarg.3
0xb244  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb249  starg.s  1
0xb24b  ldarg.1
0xb24c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingPageInformationCsom
0xb251  stloc.0
0xb252  ldloc.0
0xb253  brfalse  loc_B30D
0xb258  ldarg.2
0xb259  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0xb25e  stloc.s  4
0xb260  br       loc_B2EA
0xb265  ldloc.s  4
0xb267  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xb26c  castclass [System.Xml]System.Xml.XmlNode
0xb271  stloc.1
0xb272  ldloc.1
0xb273  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xb278  ldstr    aName// "Name"
0xb27d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xb282  stloc.2
0xb283  ldloc.2
0xb284  brfalse.s loc_B2EA
0xb286  ldloc.2
0xb287  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xb28c  stloc.3
0xb28d  ldloc.3
0xb28e  dup
0xb28f  stloc.s  5
0xb291  brfalse.s loc_B2EA
0xb293  ldloc.s  5
0xb295  ldstr    aFolder// "Folder"
0xb29a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb29f  brtrue.s loc_B2BF
0xb2a1  ldloc.s  5
0xb2a3  ldstr    aName// "Name"
0xb2a8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb2ad  brtrue.s loc_B2CE
0xb2af  ldloc.s  5
0xb2b1  ldstr    aPagelayoutlist// "PageLayoutListItem"
0xb2b6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb2bb  brtrue.s loc_B2DD
0xb2bd  br.s     loc_B2EA
0xb2bf  ldloc.0
0xb2c0  ldloc.1
0xb2c1  ldarg.3
0xb2c2  call     T0x2B000027
0xb2c7  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingPageInformationCsom::set_Folder(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder)
0xb2cc  br.s     loc_B2EA
0xb2ce  ldloc.0
0xb2cf  ldloc.1
0xb2d0  ldarg.3
0xb2d1  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb2d6  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingPageInformationCsom::set_Name(string)
0xb2db  br.s     loc_B2EA
0xb2dd  ldloc.0
0xb2de  ldloc.1
0xb2df  ldarg.3
0xb2e0  call     T0x2B000028
0xb2e5  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PublishingPageInformationCsom::set_PageLayoutListItem(class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem)
0xb2ea  ldloc.s  4
0xb2ec  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb2f1  brtrue   loc_B265
0xb2f6  leave.s  loc_B30D
0xb2f8  ldloc.s  4
0xb2fa  isinst   [mscorlib]System.IDisposable
0xb2ff  stloc.s  6
0xb301  ldloc.s  6
0xb303  brfalse.s loc_B30C
0xb305  ldloc.s  6
0xb307  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb30c  endfinally
0xb30d  ldloc.0
0xb30e  ret
```
