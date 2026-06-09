# Microsoft.SharePoint.Client.ClientMethodsProcessor::WriteQueryResults

- ea: `0xb3c0`
- end: `0xb43d`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::WriteQueryResults`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb2e0`

## callees

- `0x1600`
- `0xb3c0`
- `0xc730`
- `0xdda0`
- `0xe120`
- `0xe6c0`
- `0x152f0`

## string_xrefs

- `0xb403`: `_SerializeToJson`

## pseudocode

```c

```

## disassembly

```asm
0xb3c0  ldarg.0
0xb3c1  ldarg.1
0xb3c2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb3c7  call     instance class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ClientMethodsProcessor::GetServerStub(class [mscorlib]System.Type type)
0xb3cc  stloc.0
0xb3cd  call     bool Microsoft.SharePoint.Client.ClientMethodsProcessor::get_IsMonitoredScopeRemovalKillSwitchActive()
0xb3d2  brfalse.s loc_B3EA
0xb3d4  ldloc.0
0xb3d5  ldarg.0
0xb3d6  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb3db  ldarg.1
0xb3dc  ldarg.2
0xb3dd  ldarg.0
0xb3de  ldfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientMethodsProcessor::m_proxyContext
0xb3e3  ldc.i4.1
0xb3e4  callvirt instance void Microsoft.SharePoint.Client.ServerStub::WriteAsJsonWithMonitoredScope(class Microsoft.SharePoint.Client.JsonWriter writer, object value, class Microsoft.SharePoint.Client.ClientObjectQuery objectQuery, class Microsoft.SharePoint.Client.ProxyContext proxyContext, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0xb3e9  ret
0xb3ea  ldarg.1
0xb3eb  brtrue.s loc_B3F0
0xb3ed  ldnull
0xb3ee  br.s     loc_B3F6
0xb3f0  ldarg.1
0xb3f1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb3f6  stloc.1
0xb3f7  ldarg.0
0xb3f8  ldfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientMethodsProcessor::m_proxyContext
0xb3fd  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0xb402  ldloc.1
0xb403  ldstr    aSerializetojso// "_SerializeToJson"
0xb408  ldc.i4.1
0xb409  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0xb40e  stloc.2
0xb40f  ldloc.0
0xb410  ldarg.0
0xb411  ldfld    class Microsoft.SharePoint.Client.JsonWriter Microsoft.SharePoint.Client.ClientMethodsProcessor::m_writer
0xb416  ldarg.1
0xb417  ldarg.2
0xb418  ldarg.0
0xb419  ldfld    class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.ClientMethodsProcessor::m_proxyContext
0xb41e  ldc.i4.1
0xb41f  callvirt instance void Microsoft.SharePoint.Client.ServerStub::WriteAsJsonWithMonitoredScope(class Microsoft.SharePoint.Client.JsonWriter writer, object value, class Microsoft.SharePoint.Client.ClientObjectQuery objectQuery, class Microsoft.SharePoint.Client.ProxyContext proxyContext, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0xb424  leave.s  loc_B430
0xb426  stloc.3
0xb427  ldloc.2
0xb428  ldloc.3
0xb429  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0xb42e  rethrow
0xb430  leave.s  loc_B43C
0xb432  ldloc.2
0xb433  brfalse.s loc_B43B
0xb435  ldloc.2
0xb436  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb43b  endfinally
0xb43c  ret
```
