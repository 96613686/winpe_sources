# Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::InitFromXml

- ea: `0x1e70`
- end: `0x1f1c`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::InitFromXml`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1e70`

## pseudocode

```c

```

## disassembly

```asm
0x1e70  ldarg.0
0x1e71  ldarg.1
0x1e72  ldarg.2
0x1e73  ldarg.3
0x1e74  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1e79  starg.s  1
0x1e7b  ldarg.1
0x1e7c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse
0x1e81  stloc.0
0x1e82  ldloc.0
0x1e83  brfalse  loc_1F1A
0x1e88  ldarg.2
0x1e89  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x1e8e  stloc.s  4
0x1e90  br.s     loc_1EFA
0x1e92  ldloc.s  4
0x1e94  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1e99  castclass [System.Xml]System.Xml.XmlNode
0x1e9e  stloc.1
0x1e9f  ldloc.1
0x1ea0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1ea5  ldstr    aName// "Name"
0x1eaa  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1eaf  stloc.2
0x1eb0  ldloc.2
0x1eb1  brfalse.s loc_1EFA
0x1eb3  ldloc.2
0x1eb4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1eb9  stloc.3
0x1eba  ldloc.3
0x1ebb  dup
0x1ebc  stloc.s  5
0x1ebe  brfalse.s loc_1EFA
0x1ec0  ldloc.s  5
0x1ec2  ldstr    aSitestatus// "SiteStatus"
0x1ec7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ecc  brtrue.s loc_1EDE
0x1ece  ldloc.s  5
0x1ed0  ldstr    aSiteurl// "SiteUrl"
0x1ed5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1eda  brtrue.s loc_1EED
0x1edc  br.s     loc_1EFA
0x1ede  ldloc.0
0x1edf  ldloc.1
0x1ee0  ldarg.3
0x1ee1  call     T0x2B000009
0x1ee6  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse::set_SiteStatus(valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteStatus)
0x1eeb  br.s     loc_1EFA
0x1eed  ldloc.0
0x1eee  ldloc.1
0x1eef  ldarg.3
0x1ef0  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1ef5  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse::set_SiteUrl(string)
0x1efa  ldloc.s  4
0x1efc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f01  brtrue.s loc_1E92
0x1f03  leave.s  loc_1F1A
0x1f05  ldloc.s  4
0x1f07  isinst   [mscorlib]System.IDisposable
0x1f0c  stloc.s  6
0x1f0e  ldloc.s  6
0x1f10  brfalse.s loc_1F19
0x1f12  ldloc.s  6
0x1f14  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f19  endfinally
0x1f1a  ldloc.0
0x1f1b  ret
```
