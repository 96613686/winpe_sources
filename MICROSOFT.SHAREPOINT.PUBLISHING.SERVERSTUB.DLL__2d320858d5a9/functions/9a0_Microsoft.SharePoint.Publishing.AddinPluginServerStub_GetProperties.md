# Microsoft.SharePoint.Publishing.AddinPluginServerStub::GetProperties

- ea: `0x9a0`
- end: `0x9b8`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::GetProperties`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14260`

## pseudocode

```c

```

## disassembly

```asm
0x9a0  ldc.i4.s 0xFE
0x9a2  newobj   instance void <GetProperties>d__c::.ctor(int32 <>1__state)
0x9a7  stloc.0
0x9a8  ldloc.0
0x9a9  ldarg.0
0x9aa  stfld    class Microsoft.SharePoint.Publishing.AddinPluginServerStub <GetProperties>d__c::<>4__this
0x9af  ldloc.0
0x9b0  ldarg.1
0x9b1  stfld    class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext <GetProperties>d__c::<>3__proxyContext
0x9b6  ldloc.0
0x9b7  ret
```
