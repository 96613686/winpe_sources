# Microsoft.SharePoint.Publishing.AddinPluginServerStub::GetMethods

- ea: `0x980`
- end: `0x998`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::GetMethods`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x13e00`

## pseudocode

```c

```

## disassembly

```asm
0x980  ldc.i4.s 0xFE
0x982  newobj   instance void <GetMethods>d__1::.ctor(int32 <>1__state)
0x987  stloc.0
0x988  ldloc.0
0x989  ldarg.0
0x98a  stfld    class Microsoft.SharePoint.Publishing.AddinPluginServerStub <GetMethods>d__1::<>4__this
0x98f  ldloc.0
0x990  ldarg.1
0x991  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetMethods>d__1::<>3__proxyContext
0x996  ldloc.0
0x997  ret
```
