# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::IsSetPropertyBlocked

- ea: `0xb970`
- end: `0xb989`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::IsSetPropertyBlocked`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd60`

## callees

- `0xb970`

## pseudocode

```c

```

## disassembly

```asm
0xb970  ldarg.2
0xb971  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.ScheduledItemServerStub::s_targetTypeId
0xb976  ldarg.1
0xb977  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsSetPropertyBlocked(valuetype [mscorlib]System.Guid, string)
0xb97c  brfalse.s loc_B980
0xb97e  ldc.i4.1
0xb97f  ret
0xb980  ldarg.0
0xb981  ldarg.1
0xb982  ldarg.2
0xb983  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsSetPropertyBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb988  ret
```
