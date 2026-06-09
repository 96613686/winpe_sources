# Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::GetProperties

- ea: `0x1dd0`
- end: `0x1de8`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter::GetProperties`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x15830`

## pseudocode

```c

```

## disassembly

```asm
0x1dd0  ldc.i4.s 0xFE
0x1dd2  newobj   instance void <GetProperties>d__8::.ctor(int32 <>1__state)
0x1dd7  stloc.0
0x1dd8  ldloc.0
0x1dd9  ldarg.0
0x1dda  stfld    class Microsoft.SharePoint.Publishing.CommunicationSiteCreationRequestValueTypeConverter <GetProperties>d__8::<>4__this
0x1ddf  ldloc.0
0x1de0  ldarg.1
0x1de1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__8::<>3__proxyContext
0x1de6  ldloc.0
0x1de7  ret
```
