# Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::InitFromXml

- ea: `0x11710`
- end: `0x117bc`
- name: `Microsoft.SharePoint.Publishing.SitePageVersionInfoValueTypeConverter::InitFromXml`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11710`

## string_xrefs

- `0x11762`: `LastVersionCreated`
- `0x11770`: `LastVersionCreatedBy`

## pseudocode

```c

```

## disassembly

```asm
0x11710  ldarg.0
0x11711  ldarg.1
0x11712  ldarg.2
0x11713  ldarg.3
0x11714  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11719  starg.s  1
0x1171b  ldarg.1
0x1171c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo
0x11721  stloc.0
0x11722  ldloc.0
0x11723  brfalse  loc_117BA
0x11728  ldarg.2
0x11729  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x1172e  stloc.s  4
0x11730  br.s     loc_1179A
0x11732  ldloc.s  4
0x11734  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x11739  castclass [System.Xml]System.Xml.XmlNode
0x1173e  stloc.1
0x1173f  ldloc.1
0x11740  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x11745  ldstr    aName// "Name"
0x1174a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1174f  stloc.2
0x11750  ldloc.2
0x11751  brfalse.s loc_1179A
0x11753  ldloc.2
0x11754  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x11759  stloc.3
0x1175a  ldloc.3
0x1175b  dup
0x1175c  stloc.s  5
0x1175e  brfalse.s loc_1179A
0x11760  ldloc.s  5
0x11762  ldstr    aLastversioncre// "LastVersionCreated"
0x11767  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1176c  brtrue.s loc_1177E
0x1176e  ldloc.s  5
0x11770  ldstr    aLastversioncre_0// "LastVersionCreatedBy"
0x11775  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1177a  brtrue.s loc_1178D
0x1177c  br.s     loc_1179A
0x1177e  ldloc.0
0x1177f  ldloc.1
0x11780  ldarg.3
0x11781  call     valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToDateTime(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11786  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo::set_LastVersionCreated(valuetype [mscorlib]System.DateTime)
0x1178b  br.s     loc_1179A
0x1178d  ldloc.0
0x1178e  ldloc.1
0x1178f  ldarg.3
0x11790  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11795  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageVersionInfo::set_LastVersionCreatedBy(string)
0x1179a  ldloc.s  4
0x1179c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x117a1  brtrue.s loc_11732
0x117a3  leave.s  loc_117BA
0x117a5  ldloc.s  4
0x117a7  isinst   [mscorlib]System.IDisposable
0x117ac  stloc.s  6
0x117ae  ldloc.s  6
0x117b0  brfalse.s loc_117B9
0x117b2  ldloc.s  6
0x117b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x117b9  endfinally
0x117ba  ldloc.0
0x117bb  ret
```
