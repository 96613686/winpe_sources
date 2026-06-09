# Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsEntityWithMonitoredScope

- ea: `0x1f7c0`
- end: `0x1f812`
- name: `Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsEntityWithMonitoredScope`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1f3a0`

## callees

- `0xa30`
- `0xe110`
- `0xe6c0`
- `0x152f0`
- `0x1f380`
- `0x1f7c0`
- `0x1f820`

## string_xrefs

- `0x1f7d4`: `_WriteAsEntity`

## pseudocode

```c

```

## disassembly

```asm
0x1f7c0  call     bool Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::get_IsMonitoredScopeRemovalKillSwitchActive()
0x1f7c5  brfalse.s loc_1F804
0x1f7c7  ldarg.s  5
0x1f7c9  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1f7ce  ldarg.1
0x1f7cf  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x1f7d4  ldstr    aWriteasentity// "_WriteAsEntity"
0x1f7d9  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName)
0x1f7de  stloc.0
0x1f7df  ldarg.0
0x1f7e0  ldarg.1
0x1f7e1  ldarg.2
0x1f7e2  ldarg.3
0x1f7e3  ldarg.s  4
0x1f7e5  ldarg.s  5
0x1f7e7  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsEntity(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f7ec  leave.s  loc_1F7F8
0x1f7ee  stloc.1
0x1f7ef  ldloc.0
0x1f7f0  ldloc.1
0x1f7f1  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x1f7f6  rethrow
0x1f7f8  leave.s  loc_1F811
0x1f7fa  ldloc.0
0x1f7fb  brfalse.s loc_1F803
0x1f7fd  ldloc.0
0x1f7fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f803  endfinally
0x1f804  ldarg.0
0x1f805  ldarg.1
0x1f806  ldarg.2
0x1f807  ldarg.3
0x1f808  ldarg.s  4
0x1f80a  ldarg.s  5
0x1f80c  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::WriteAsEntity(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1f811  ret
```
