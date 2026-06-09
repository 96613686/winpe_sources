# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Status_MethodProxy

- ea: `0x2180`
- end: `0x2198`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Status_MethodProxy`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x21a0`

## pseudocode

```c

```

## disassembly

```asm
0x2180  ldarg.1
0x2181  ldc.i4.0
0x2182  call     class [System.Xml]System.Xml.XmlNode [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetArgument(class [System.Xml]System.Xml.XmlNodeList, int32)
0x2187  stloc.0
0x2188  ldloc.0
0x2189  ldarg.2
0x218a  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x218f  stloc.1
0x2190  ldarg.0
0x2191  ldloc.1
0x2192  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite::GetSiteStatus(string)
0x2197  ret
```
