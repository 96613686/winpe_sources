# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::IsMethodBlocked

- ea: `0x2280`
- end: `0x2299`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::IsMethodBlocked`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2280`

## pseudocode

```c

```

## disassembly

```asm
0x2280  ldarg.2
0x2281  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::s_targetTypeId
0x2286  ldarg.1
0x2287  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsMethodBlocked(valuetype [mscorlib]System.Guid, string)
0x228c  brfalse.s loc_2290
0x228e  ldc.i4.1
0x228f  ret
0x2290  ldarg.0
0x2291  ldarg.1
0x2292  ldarg.2
0x2293  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsMethodBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2298  ret
```
