# Microsoft.SharePoint.Publishing.SiteSharingEmailContextValueTypeConverter::InitFromXml

- ea: `0x11f10`
- end: `0x11fff`
- name: `Microsoft.SharePoint.Publishing.SiteSharingEmailContextValueTypeConverter::InitFromXml`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11f10`

## pseudocode

```c

```

## disassembly

```asm
0x11f10  ldarg.0
0x11f11  ldarg.1
0x11f12  ldarg.2
0x11f13  ldarg.3
0x11f14  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::InitFromXml(object, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11f19  starg.s  1
0x11f1b  ldarg.1
0x11f1c  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteSharingEmailContext
0x11f21  stloc.0
0x11f22  ldloc.0
0x11f23  brfalse  loc_11FFD
0x11f28  ldarg.2
0x11f29  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNode::GetEnumerator()
0x11f2e  stloc.s  4
0x11f30  br       loc_11FDA
0x11f35  ldloc.s  4
0x11f37  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x11f3c  castclass [System.Xml]System.Xml.XmlNode
0x11f41  stloc.1
0x11f42  ldloc.1
0x11f43  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x11f48  ldstr    aName// "Name"
0x11f4d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x11f52  stloc.2
0x11f53  ldloc.2
0x11f54  brfalse  loc_11FDA
0x11f59  ldloc.2
0x11f5a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x11f5f  stloc.3
0x11f60  ldloc.3
0x11f61  dup
0x11f62  stloc.s  5
0x11f64  brfalse.s loc_11FDA
0x11f66  ldloc.s  5
0x11f68  ldstr    aCustomdescript// "CustomDescription"
0x11f6d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11f72  brtrue.s loc_11FA0
0x11f74  ldloc.s  5
0x11f76  ldstr    aCustomtitle// "CustomTitle"
0x11f7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11f80  brtrue.s loc_11FAF
0x11f82  ldloc.s  5
0x11f84  ldstr    aMessage_0// "Message"
0x11f89  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11f8e  brtrue.s loc_11FBE
0x11f90  ldloc.s  5
0x11f92  ldstr    aUrl// "Url"
0x11f97  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11f9c  brtrue.s loc_11FCD
0x11f9e  br.s     loc_11FDA
0x11fa0  ldloc.0
0x11fa1  ldloc.1
0x11fa2  ldarg.3
0x11fa3  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11fa8  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteSharingEmailContext::set_CustomDescription(string)
0x11fad  br.s     loc_11FDA
0x11faf  ldloc.0
0x11fb0  ldloc.1
0x11fb1  ldarg.3
0x11fb2  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11fb7  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteSharingEmailContext::set_CustomTitle(string)
0x11fbc  br.s     loc_11FDA
0x11fbe  ldloc.0
0x11fbf  ldloc.1
0x11fc0  ldarg.3
0x11fc1  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11fc6  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteSharingEmailContext::set_Message(string)
0x11fcb  br.s     loc_11FDA
0x11fcd  ldloc.0
0x11fce  ldloc.1
0x11fcf  ldarg.3
0x11fd0  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11fd5  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteSharingEmailContext::set_Url(string)
0x11fda  ldloc.s  4
0x11fdc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11fe1  brtrue   loc_11F35
0x11fe6  leave.s  loc_11FFD
0x11fe8  ldloc.s  4
0x11fea  isinst   [mscorlib]System.IDisposable
0x11fef  stloc.s  6
0x11ff1  ldloc.s  6
0x11ff3  brfalse.s loc_11FFC
0x11ff5  ldloc.s  6
0x11ff7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11ffc  endfinally
0x11ffd  ldloc.0
0x11ffe  ret
```
