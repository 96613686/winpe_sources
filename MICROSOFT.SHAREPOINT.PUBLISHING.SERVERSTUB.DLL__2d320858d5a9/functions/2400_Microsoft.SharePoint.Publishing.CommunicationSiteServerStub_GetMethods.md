# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::GetMethods

- ea: `0x2400`
- end: `0x2418`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::GetMethods`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x16100`

## pseudocode

```c

```

## disassembly

```asm
0x2400  ldc.i4.s 0xFE
0x2402  newobj   instance void <GetMethods>d__5::.ctor(int32 <>1__state)
0x2407  stloc.0
0x2408  ldloc.0
0x2409  ldarg.0
0x240a  stfld    class Microsoft.SharePoint.Publishing.CommunicationSiteServerStub <GetMethods>d__5::<>4__this
0x240f  ldloc.0
0x2410  ldarg.1
0x2411  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__5::<>3__proxyContext
0x2416  ldloc.0
0x2417  ret
```
