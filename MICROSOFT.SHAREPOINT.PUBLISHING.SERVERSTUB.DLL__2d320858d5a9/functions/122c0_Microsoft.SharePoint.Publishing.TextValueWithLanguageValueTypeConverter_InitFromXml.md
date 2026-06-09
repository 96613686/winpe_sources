# Microsoft.SharePoint.Publishing.TextValueWithLanguageValueTypeConverter::InitFromXml

- ea: `0x122c0`
- end: `0x1238f`
- name: `Microsoft.SharePoint.Publishing.TextValueWithLanguageValueTypeConverter::InitFromXml`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x122c0`

## pseudocode

```c

```

## disassembly

```asm
0x122c0  ldarg.0
0x122c1  ldarg.1
0x122c2  ldarg.2
0x122c3  ldarg.3
0x122c4  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x122c9  starg.s  1
0x122cb  ldarg.1
0x122cc  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/TextValueWithLanguage
0x122d1  stloc.0
0x122d2  ldloc.0
0x122d3  brfalse  loc_1238D
0x122d8  ldarg.2
0x122d9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x122de  stloc.s  4
0x122e0  br       loc_1236A
0x122e5  ldloc.s  4
0x122e7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x122ec  castclass [System.Xml]System.Xml.XmlNode
0x122f1  stloc.1
0x122f2  ldloc.1
0x122f3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x122f8  ldstr    aName// "Name"
0x122fd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x12302  stloc.2
0x12303  ldloc.2
0x12304  brfalse.s loc_1236A
0x12306  ldloc.2
0x12307  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1230c  stloc.3
0x1230d  ldloc.3
0x1230e  dup
0x1230f  stloc.s  5
0x12311  brfalse.s loc_1236A
0x12313  ldloc.s  5
0x12315  ldstr    aColorseed// "ColorSeed"
0x1231a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1231f  brtrue.s loc_1233F
0x12321  ldloc.s  5
0x12323  ldstr    aLcid// "Lcid"
0x12328  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1232d  brtrue.s loc_1234E
0x1232f  ldloc.s  5
0x12331  ldstr    aText// "Text"
0x12336  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1233b  brtrue.s loc_1235D
0x1233d  br.s     loc_1236A
0x1233f  ldloc.0
0x12340  ldloc.1
0x12341  ldarg.3
0x12342  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12347  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/TextValueWithLanguage::set_ColorSeed(string)
0x1234c  br.s     loc_1236A
0x1234e  ldloc.0
0x1234f  ldloc.1
0x12350  ldarg.3
0x12351  call     int32 [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToInt32(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12356  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/TextValueWithLanguage::set_Lcid(int32)
0x1235b  br.s     loc_1236A
0x1235d  ldloc.0
0x1235e  ldloc.1
0x1235f  ldarg.3
0x12360  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x12365  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/TextValueWithLanguage::set_Text(string)
0x1236a  ldloc.s  4
0x1236c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12371  brtrue   loc_122E5
0x12376  leave.s  loc_1238D
0x12378  ldloc.s  4
0x1237a  isinst   [mscorlib]System.IDisposable
0x1237f  stloc.s  6
0x12381  ldloc.s  6
0x12383  brfalse.s loc_1238C
0x12385  ldloc.s  6
0x12387  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1238c  endfinally
0x1238d  ldloc.0
0x1238e  ret
```
