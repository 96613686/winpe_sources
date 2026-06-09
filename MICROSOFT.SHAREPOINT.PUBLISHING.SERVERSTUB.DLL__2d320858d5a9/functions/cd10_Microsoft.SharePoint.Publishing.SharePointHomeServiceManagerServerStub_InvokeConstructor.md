# Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::InvokeConstructor

- ea: `0xcd10`
- end: `0xcd32`
- name: `Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::InvokeConstructor`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xcd00`
- `0xcd10`

## pseudocode

```c

```

## disassembly

```asm
0xcd10  ldarg.2
0xcd11  brtrue.s loc_CD1E
0xcd13  ldstr    aProxycontext// "proxyContext"
0xcd18  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcd1d  throw
0xcd1e  ldarg.0
0xcd1f  ldstr    aCtor// ".ctor"
0xcd24  ldarg.2
0xcd25  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xcd2a  ldarg.1
0xcd2b  ldarg.2
0xcd2c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::SharePointHomeServiceManager_ConProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xcd31  ret
```
