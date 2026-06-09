# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Create_MethodProxy

- ea: `0x2160`
- end: `0x2178`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Create_MethodProxy`
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
0x2160  ldarg.1
0x2161  ldc.i4.0
0x2162  call     class [System.Xml]System.Xml.XmlNode [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetArgument(class [System.Xml]System.Xml.XmlNodeList, int32)
0x2167  stloc.0
0x2168  ldloc.0
0x2169  ldarg.2
0x216a  call     T0x2B00000C
0x216f  stloc.1
0x2170  ldarg.0
0x2171  ldloc.1
0x2172  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite::Create(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequest)
0x2177  ret
```
