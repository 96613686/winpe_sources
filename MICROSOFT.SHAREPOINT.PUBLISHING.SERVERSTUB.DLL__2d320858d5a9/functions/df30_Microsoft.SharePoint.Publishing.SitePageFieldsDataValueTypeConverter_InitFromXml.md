# Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::InitFromXml

- ea: `0xdf30`
- end: `0xe05c`
- name: `Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::InitFromXml`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xdf30`

## string_xrefs

- `0xdfa7`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0xdf30  ldarg.0
0xdf31  ldarg.1
0xdf32  ldarg.2
0xdf33  ldarg.3
0xdf34  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xdf39  starg.s  1
0xdf3b  ldarg.1
0xdf3c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData
0xdf41  stloc.0
0xdf42  ldloc.0
0xdf43  brfalse  loc_E05A
0xdf48  ldarg.2
0xdf49  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0xdf4e  stloc.s  4
0xdf50  br       loc_E037
0xdf55  ldloc.s  4
0xdf57  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xdf5c  castclass [System.Xml]System.Xml.XmlNode
0xdf61  stloc.1
0xdf62  ldloc.1
0xdf63  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xdf68  ldstr    aName// "Name"
0xdf6d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xdf72  stloc.2
0xdf73  ldloc.2
0xdf74  brfalse  loc_E037
0xdf79  ldloc.2
0xdf7a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xdf7f  stloc.3
0xdf80  ldloc.3
0xdf81  dup
0xdf82  stloc.s  5
0xdf84  brfalse  loc_E037
0xdf89  ldloc.s  5
0xdf8b  ldstr    aBannerimageurl// "BannerImageUrl"
0xdf90  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdf95  brtrue.s loc_DFDF
0xdf97  ldloc.s  5
0xdf99  ldstr    aCanvascontent1// "CanvasContent1"
0xdf9e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfa3  brtrue.s loc_DFEE
0xdfa5  ldloc.s  5
0xdfa7  ldstr    aCanvasjson1// "CanvasJson1"
0xdfac  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfb1  brtrue.s loc_DFFD
0xdfb3  ldloc.s  5
0xdfb5  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0xdfba  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfbf  brtrue.s loc_E00C
0xdfc1  ldloc.s  5
0xdfc3  ldstr    aModified// "Modified"
0xdfc8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfcd  brtrue.s loc_E01B
0xdfcf  ldloc.s  5
0xdfd1  ldstr    aTitle// "Title"
0xdfd6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xdfdb  brtrue.s loc_E02A
0xdfdd  br.s     loc_E037
0xdfdf  ldloc.0
0xdfe0  ldloc.1
0xdfe1  ldarg.3
0xdfe2  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xdfe7  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_BannerImageUrl(string)
0xdfec  br.s     loc_E037
0xdfee  ldloc.0
0xdfef  ldloc.1
0xdff0  ldarg.3
0xdff1  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xdff6  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_CanvasContent1(string)
0xdffb  br.s     loc_E037
0xdffd  ldloc.0
0xdffe  ldloc.1
0xdfff  ldarg.3
0xe000  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe005  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_CanvasJson1(string)
0xe00a  br.s     loc_E037
0xe00c  ldloc.0
0xe00d  ldloc.1
0xe00e  ldarg.3
0xe00f  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe014  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_LayoutWebpartsContent(string)
0xe019  br.s     loc_E037
0xe01b  ldloc.0
0xe01c  ldloc.1
0xe01d  ldarg.3
0xe01e  call     valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToDateTime(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe023  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_Modified(valuetype [mscorlib]System.DateTime)
0xe028  br.s     loc_E037
0xe02a  ldloc.0
0xe02b  ldloc.1
0xe02c  ldarg.3
0xe02d  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe032  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_Title(string)
0xe037  ldloc.s  4
0xe039  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe03e  brtrue   loc_DF55
0xe043  leave.s  loc_E05A
0xe045  ldloc.s  4
0xe047  isinst   [mscorlib]System.IDisposable
0xe04c  stloc.s  6
0xe04e  ldloc.s  6
0xe050  brfalse.s loc_E059
0xe052  ldloc.s  6
0xe054  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe059  endfinally
0xe05a  ldloc.0
0xe05b  ret
```
