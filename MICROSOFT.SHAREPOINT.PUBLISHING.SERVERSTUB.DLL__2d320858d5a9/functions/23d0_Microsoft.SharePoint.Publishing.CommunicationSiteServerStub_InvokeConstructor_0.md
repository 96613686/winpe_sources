# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::InvokeConstructor_0

- ea: `0x23d0`
- end: `0x23f2`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::InvokeConstructor_0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x23c0`
- `0x23d0`

## pseudocode

```c

```

## disassembly

```asm
0x23d0  ldarg.2
0x23d1  brtrue.s loc_23DE
0x23d3  ldstr    aProxycontext// "proxyContext"
0x23d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x23dd  throw
0x23de  ldarg.0
0x23df  ldstr    aCtor// ".ctor"
0x23e4  ldarg.2
0x23e5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x23ea  ldarg.1
0x23eb  ldarg.2
0x23ec  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::CommunicationSite_ConProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x23f1  ret
```
