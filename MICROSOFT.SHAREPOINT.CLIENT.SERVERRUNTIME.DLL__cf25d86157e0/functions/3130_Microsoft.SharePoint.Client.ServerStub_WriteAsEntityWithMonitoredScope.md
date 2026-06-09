# Microsoft.SharePoint.Client.ServerStub::WriteAsEntityWithMonitoredScope

- ea: `0x3130`
- end: `0x3184`
- name: `Microsoft.SharePoint.Client.ServerStub::WriteAsEntityWithMonitoredScope`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x2d70`

## callees

- `0xa30`
- `0x3130`
- `0x3190`
- `0x3a40`
- `0xe120`
- `0xe6c0`
- `0x152f0`

## string_xrefs

- `0x3144`: `_WriteAsEntity`

## pseudocode

```c

```

## disassembly

```asm
0x3130  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0x3135  brfalse.s loc_3176
0x3137  ldarg.s  5
0x3139  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x313e  ldarg.0
0x313f  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x3144  ldstr    aWriteasentity// "_WriteAsEntity"
0x3149  ldarg.s  6
0x314b  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x3150  stloc.0
0x3151  ldarg.0
0x3152  ldarg.1
0x3153  ldarg.2
0x3154  ldarg.3
0x3155  ldarg.s  4
0x3157  ldarg.s  5
0x3159  call     instance void Microsoft.SharePoint.Client.ServerStub::WriteAsEntity(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x315e  leave.s  loc_316A
0x3160  stloc.1
0x3161  ldloc.0
0x3162  ldloc.1
0x3163  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x3168  rethrow
0x316a  leave.s  loc_3183
0x316c  ldloc.0
0x316d  brfalse.s loc_3175
0x316f  ldloc.0
0x3170  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3175  endfinally
0x3176  ldarg.0
0x3177  ldarg.1
0x3178  ldarg.2
0x3179  ldarg.3
0x317a  ldarg.s  4
0x317c  ldarg.s  5
0x317e  call     instance void Microsoft.SharePoint.Client.ServerStub::WriteAsEntity(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x3183  ret
```
