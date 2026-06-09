# Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeConstructor_0

- ea: `0x11480`
- end: `0x114a2`
- name: `Microsoft.SharePoint.Publishing.SitePageServiceServerStub::InvokeConstructor_0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x11470`
- `0x11480`

## pseudocode

```c

```

## disassembly

```asm
0x11480  ldarg.2
0x11481  brtrue.s loc_1148E
0x11483  ldstr    aProxycontext// "proxyContext"
0x11488  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1148d  throw
0x1148e  ldarg.0
0x1148f  ldstr    aCtor// ".ctor"
0x11494  ldarg.2
0x11495  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1149a  ldarg.1
0x1149b  ldarg.2
0x1149c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageService Microsoft.SharePoint.Publishing.SitePageServiceServerStub::SitePageService_ConProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x114a1  ret
```
