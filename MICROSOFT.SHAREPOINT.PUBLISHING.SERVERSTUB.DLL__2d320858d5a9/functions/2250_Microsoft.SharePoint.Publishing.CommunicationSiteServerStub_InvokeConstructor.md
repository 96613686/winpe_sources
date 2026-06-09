# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::InvokeConstructor

- ea: `0x2250`
- end: `0x2272`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::InvokeConstructor`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2240`
- `0x2250`

## pseudocode

```c

```

## disassembly

```asm
0x2250  ldarg.2
0x2251  brtrue.s loc_225E
0x2253  ldstr    aProxycontext// "proxyContext"
0x2258  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x225d  throw
0x225e  ldarg.0
0x225f  ldstr    aCtor// ".ctor"
0x2264  ldarg.2
0x2265  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x226a  ldarg.1
0x226b  ldarg.2
0x226c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::CommunicationSite_ConProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2271  ret
```
