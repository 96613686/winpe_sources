# Microsoft.SharePoint.Publishing.EmbedServiceServerStub::InvokeConstructor

- ea: `0x4b00`
- end: `0x4b22`
- name: `Microsoft.SharePoint.Publishing.EmbedServiceServerStub::InvokeConstructor`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4af0`
- `0x4b00`

## pseudocode

```c

```

## disassembly

```asm
0x4b00  ldarg.2
0x4b01  brtrue.s loc_4B0E
0x4b03  ldstr    aProxycontext// "proxyContext"
0x4b08  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4b0d  throw
0x4b0e  ldarg.0
0x4b0f  ldstr    aCtor// ".ctor"
0x4b14  ldarg.2
0x4b15  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b1a  ldarg.1
0x4b1b  ldarg.2
0x4b1c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedService Microsoft.SharePoint.Publishing.EmbedServiceServerStub::EmbedService_ConProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4b21  ret
```
