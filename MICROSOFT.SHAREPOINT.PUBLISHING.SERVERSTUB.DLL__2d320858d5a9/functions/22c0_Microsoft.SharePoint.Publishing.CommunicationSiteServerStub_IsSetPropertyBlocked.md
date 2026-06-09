# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::IsSetPropertyBlocked

- ea: `0x22c0`
- end: `0x22d9`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::IsSetPropertyBlocked`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x22c0`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  ldarg.2
0x22c1  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::s_targetTypeId
0x22c6  ldarg.1
0x22c7  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsSetPropertyBlocked(valuetype [mscorlib]System.Guid, string)
0x22cc  brfalse.s loc_22D0
0x22ce  ldc.i4.1
0x22cf  ret
0x22d0  ldarg.0
0x22d1  ldarg.1
0x22d2  ldarg.2
0x22d3  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsSetPropertyBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x22d8  ret
```
