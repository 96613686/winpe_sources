# Microsoft.SharePoint.Publishing.AddinPluginServerStub::InvokeConstructor_0

- ea: `0x880`
- end: `0x8a2`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::InvokeConstructor_0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x870`
- `0x880`

## pseudocode

```c

```

## disassembly

```asm
0x880  ldarg.2
0x881  brtrue.s loc_88E
0x883  ldstr    aProxycontext// "proxyContext"
0x888  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x88d  throw
0x88e  ldarg.0
0x88f  ldstr    aCtor// ".ctor"
0x894  ldarg.2
0x895  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x89a  ldarg.1
0x89b  ldarg.2
0x89c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin Microsoft.SharePoint.Publishing.AddinPluginServerStub::AddinPlugin_ConProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8a1  ret
```
