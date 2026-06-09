# Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::GetProperties

- ea: `0x20b0`
- end: `0x20c8`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::GetProperties`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x15bb0`

## pseudocode

```c

```

## disassembly

```asm
0x20b0  ldc.i4.s 0xFE
0x20b2  newobj   instance void <GetProperties>d__2::.ctor(int32 <>1__state)
0x20b7  stloc.0
0x20b8  ldloc.0
0x20b9  ldarg.0
0x20ba  stfld    class Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter <GetProperties>d__2::<>4__this
0x20bf  ldloc.0
0x20c0  ldarg.1
0x20c1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__2::<>3__proxyContext
0x20c6  ldloc.0
0x20c7  ret
```
