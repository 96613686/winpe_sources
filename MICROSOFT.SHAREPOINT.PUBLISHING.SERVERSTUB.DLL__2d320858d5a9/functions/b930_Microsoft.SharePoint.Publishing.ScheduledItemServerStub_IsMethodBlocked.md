# Microsoft.SharePoint.Publishing.ScheduledItemServerStub::IsMethodBlocked

- ea: `0xb930`
- end: `0xb949`
- name: `Microsoft.SharePoint.Publishing.ScheduledItemServerStub::IsMethodBlocked`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd20`

## callees

- `0xb930`

## pseudocode

```c

```

## disassembly

```asm
0xb930  ldarg.2
0xb931  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Publishing.ScheduledItemServerStub::s_targetTypeId
0xb936  ldarg.1
0xb937  callvirt instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext::IsMethodBlocked(valuetype [mscorlib]System.Guid, string)
0xb93c  brfalse.s loc_B940
0xb93e  ldc.i4.1
0xb93f  ret
0xb940  ldarg.0
0xb941  ldarg.1
0xb942  ldarg.2
0xb943  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::IsMethodBlocked(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xb948  ret
```
