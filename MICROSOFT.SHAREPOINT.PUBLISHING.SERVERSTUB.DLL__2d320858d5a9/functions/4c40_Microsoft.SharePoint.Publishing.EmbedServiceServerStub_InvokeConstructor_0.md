# Microsoft.SharePoint.Publishing.EmbedServiceServerStub::InvokeConstructor_0

- ea: `0x4c40`
- end: `0x4c62`
- name: `Microsoft.SharePoint.Publishing.EmbedServiceServerStub::InvokeConstructor_0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4c30`
- `0x4c40`

## pseudocode

```c

```

## disassembly

```asm
0x4c40  ldarg.2
0x4c41  brtrue.s loc_4C4E
0x4c43  ldstr    aProxycontext// "proxyContext"
0x4c48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4c4d  throw
0x4c4e  ldarg.0
0x4c4f  ldstr    aCtor// ".ctor"
0x4c54  ldarg.2
0x4c55  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c5a  ldarg.1
0x4c5b  ldarg.2
0x4c5c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedService Microsoft.SharePoint.Publishing.EmbedServiceServerStub::EmbedService_ConProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4c61  ret
```
