# Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::InvokeConstructor_0

- ea: `0xce40`
- end: `0xce62`
- name: `Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::InvokeConstructor_0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xce30`
- `0xce40`

## pseudocode

```c

```

## disassembly

```asm
0xce40  ldarg.2
0xce41  brtrue.s loc_CE4E
0xce43  ldstr    aProxycontext// "proxyContext"
0xce48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xce4d  throw
0xce4e  ldarg.0
0xce4f  ldstr    aCtor// ".ctor"
0xce54  ldarg.2
0xce55  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xce5a  ldarg.1
0xce5b  ldarg.2
0xce5c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::SharePointHomeServiceManager_ConProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xce61  ret
```
