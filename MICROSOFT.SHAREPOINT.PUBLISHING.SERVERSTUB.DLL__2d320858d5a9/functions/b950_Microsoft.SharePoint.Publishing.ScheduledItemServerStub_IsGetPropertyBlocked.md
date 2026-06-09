# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::IsGetPropertyBlocked

- ea: `0xb950`
- end: `0xb969`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::IsGetPropertyBlocked`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd40`

## callees

- `0xb950`

## pseudocode

```c

```

## disassembly

```asm
0xb950  ldarg.2
0xb951  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.ScheduledItemServerStub::s_targetTypeId
0xb956  ldarg.1
0xb957  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsGetPropertyBlocked(valuetype [mscorlib]System.Guid, string)
0xb95c  brfalse.s loc_B960
0xb95e  ldc.i4.1
0xb95f  ret
0xb960  ldarg.0
0xb961  ldarg.1
0xb962  ldarg.2
0xb963  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsGetPropertyBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb968  ret
```
