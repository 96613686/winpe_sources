# Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::InitFromXml

- ea: `0xa880`
- end: `0xa98f`
- name: `Microsoft.SharePoint.Publishing.PageLayoutCreationInformationValueTypeConverter::InitFromXml`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa880`

## string_xrefs

- `0xa8f7`: `NewPageLayoutEditablePath`
- `0xa905`: `NewPageLayoutNameWithoutExtension`

## pseudocode

```c

```

## disassembly

```asm
0xa880  ldarg.0
0xa881  ldarg.1
0xa882  ldarg.2
0xa883  ldarg.3
0xa884  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa889  starg.s  1
0xa88b  ldarg.1
0xa88c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation
0xa891  stloc.0
0xa892  ldloc.0
0xa893  brfalse  loc_A98D
0xa898  ldarg.2
0xa899  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0xa89e  stloc.s  4
0xa8a0  br       loc_A96A
0xa8a5  ldloc.s  4
0xa8a7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa8ac  castclass [System.Xml]System.Xml.XmlNode
0xa8b1  stloc.1
0xa8b2  ldloc.1
0xa8b3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa8b8  ldstr    aName// "Name"
0xa8bd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa8c2  stloc.2
0xa8c3  ldloc.2
0xa8c4  brfalse  loc_A96A
0xa8c9  ldloc.2
0xa8ca  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xa8cf  stloc.3
0xa8d0  ldloc.3
0xa8d1  dup
0xa8d2  stloc.s  5
0xa8d4  brfalse  loc_A96A
0xa8d9  ldloc.s  5
0xa8db  ldstr    aAssociatedcont// "AssociatedContentTypeId"
0xa8e0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa8e5  brtrue.s loc_A921
0xa8e7  ldloc.s  5
0xa8e9  ldstr    aMasterpageurl// "MasterPageUrl"
0xa8ee  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa8f3  brtrue.s loc_A930
0xa8f5  ldloc.s  5
0xa8f7  ldstr    aNewpagelayoute// "NewPageLayoutEditablePath"
0xa8fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa901  brtrue.s loc_A93F
0xa903  ldloc.s  5
0xa905  ldstr    aNewpagelayoutn// "NewPageLayoutNameWithoutExtension"
0xa90a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa90f  brtrue.s loc_A94E
0xa911  ldloc.s  5
0xa913  ldstr    aWeb_0// "Web"
0xa918  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa91d  brtrue.s loc_A95D
0xa91f  br.s     loc_A96A
0xa921  ldloc.0
0xa922  ldloc.1
0xa923  ldarg.3
0xa924  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa929  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_AssociatedContentTypeId(string)
0xa92e  br.s     loc_A96A
0xa930  ldloc.0
0xa931  ldloc.1
0xa932  ldarg.3
0xa933  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa938  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_MasterPageUrl(string)
0xa93d  br.s     loc_A96A
0xa93f  ldloc.0
0xa940  ldloc.1
0xa941  ldarg.3
0xa942  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa947  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_NewPageLayoutEditablePath(string)
0xa94c  br.s     loc_A96A
0xa94e  ldloc.0
0xa94f  ldloc.1
0xa950  ldarg.3
0xa951  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa956  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_NewPageLayoutNameWithoutExtension(string)
0xa95b  br.s     loc_A96A
0xa95d  ldloc.0
0xa95e  ldloc.1
0xa95f  ldarg.3
0xa960  call     T0x2B000019
0xa965  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageLayoutCreationInformation::set_Web(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0xa96a  ldloc.s  4
0xa96c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa971  brtrue   loc_A8A5
0xa976  leave.s  loc_A98D
0xa978  ldloc.s  4
0xa97a  isinst   [mscorlib]System.IDisposable
0xa97f  stloc.s  6
0xa981  ldloc.s  6
0xa983  brfalse.s loc_A98C
0xa985  ldloc.s  6
0xa987  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa98c  endfinally
0xa98d  ldloc.0
0xa98e  ret
```
