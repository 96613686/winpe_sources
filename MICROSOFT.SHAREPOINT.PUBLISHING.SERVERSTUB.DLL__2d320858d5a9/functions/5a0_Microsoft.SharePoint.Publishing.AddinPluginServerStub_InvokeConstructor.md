# Microsoft.SharePoint.Publishing.AddinPluginServerStub::InvokeConstructor

- ea: `0x5a0`
- end: `0x5c2`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::InvokeConstructor`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x590`
- `0x5a0`

## pseudocode

```c

```

## disassembly

```asm
0x5a0  ldarg.2
0x5a1  brtrue.s loc_5AE
0x5a3  ldstr    aProxycontext// "proxyContext"
0x5a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ad  throw
0x5ae  ldarg.0
0x5af  ldstr    aCtor// ".ctor"
0x5b4  ldarg.2
0x5b5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ba  ldarg.1
0x5bb  ldarg.2
0x5bc  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin Microsoft.SharePoint.Publishing.AddinPluginServerStub::AddinPlugin_ConProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5c1  ret
```
