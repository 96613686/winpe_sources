# Microsoft.SharePoint.Client.ServerStub::WriteAsJsonWithMonitoredScope

- ea: `0x1600`
- end: `0x1650`
- name: `Microsoft.SharePoint.Client.ServerStub::WriteAsJsonWithMonitoredScope`
- size: `80`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16e0`
- `0x2630`
- `0xb3c0`
- `0x11ef0`

## callees

- `0xa30`
- `0xf30`
- `0x1600`
- `0x3a40`
- `0xe120`
- `0xe6c0`
- `0x152f0`

## string_xrefs

- `0x1614`: `_SerializeToJson`

## pseudocode

```c

```

## disassembly

```asm
0x1600  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0x1605  brfalse.s loc_1644
0x1607  ldarg.s  4
0x1609  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x160e  ldarg.0
0x160f  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x1614  ldstr    aSerializetojso// "_SerializeToJson"
0x1619  ldarg.s  5
0x161b  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x1620  stloc.0
0x1621  ldarg.0
0x1622  ldarg.1
0x1623  ldarg.2
0x1624  ldarg.3
0x1625  ldarg.s  4
0x1627  callvirt instance void Microsoft.SharePoint.Client.ServerStub::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ClientObjectQuery objectQuery, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x162c  leave.s  loc_1638
0x162e  stloc.1
0x162f  ldloc.0
0x1630  ldloc.1
0x1631  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x1636  rethrow
0x1638  leave.s  loc_164F
0x163a  ldloc.0
0x163b  brfalse.s loc_1643
0x163d  ldloc.0
0x163e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1643  endfinally
0x1644  ldarg.0
0x1645  ldarg.1
0x1646  ldarg.2
0x1647  ldarg.3
0x1648  ldarg.s  4
0x164a  callvirt instance void Microsoft.SharePoint.Client.ServerStub::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ClientObjectQuery objectQuery, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x164f  ret
```
