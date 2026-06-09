# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeConstructor

- ea: `0x10ff0`
- end: `0x11012`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeConstructor`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x10fe0`
- `0x10ff0`

## pseudocode

```c

```

## disassembly

```asm
0x10ff0  ldarg.2
0x10ff1  brtrue.s loc_10FFE
0x10ff3  ldstr    aProxycontext// "proxyContext"
0x10ff8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10ffd  throw
0x10ffe  ldarg.0
0x10fff  ldstr    aCtor// ".ctor"
0x11004  ldarg.2
0x11005  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1100a  ldarg.1
0x1100b  ldarg.2
0x1100c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService Microsoft.SharePoint.Publishing.SitePageServiceServerStub::SitePageService_ConProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11011  ret
```
