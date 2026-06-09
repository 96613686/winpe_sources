# Microsoft.SharePoint.Client.ServerStub::WriteQueryResult

- ea: `0x2630`
- end: `0x2683`
- name: `Microsoft.SharePoint.Client.ServerStub::WriteQueryResult`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x344c0`

## callees

- `0x1600`
- `0x2630`
- `0x13410`
- `0x152f0`
- `0x16920`
- `0x17080`

## string_xrefs

- `0x2633`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x2630  ldarg.1
0x2631  brtrue.s loc_263E
0x2633  ldstr    aWriter// "writer"
0x2638  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x263d  throw
0x263e  ldarg.s  4
0x2640  brtrue.s loc_264D
0x2642  ldstr    aProxycontext// "proxyContext"
0x2647  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x264c  throw
0x264d  ldarg.2
0x264e  brtrue.s loc_2657
0x2650  ldarg.1
0x2651  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x2656  ret
0x2657  ldarg.2
0x2658  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x265d  stloc.0
0x265e  ldloc.0
0x265f  ldarg.s  4
0x2661  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x2666  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x266b  stloc.1
0x266c  ldloc.1
0x266d  brtrue.s loc_2676
0x266f  ldloc.0
0x2670  newobj   instance void Microsoft.SharePoint.Client.ServerProxyNotFoundException::.ctor(class [mscorlib]System.Type type)
0x2675  throw
0x2676  ldloc.1
0x2677  ldarg.1
0x2678  ldarg.2
0x2679  ldarg.3
0x267a  ldarg.s  4
0x267c  ldc.i4.1
0x267d  callvirt instance void Microsoft.SharePoint.Client.ServerStub::WriteAsJsonWithMonitoredScope(class Microsoft.SharePoint.Client.JsonWriter writer, object value, class Microsoft.SharePoint.Client.ClientObjectQuery objectQuery, class Microsoft.SharePoint.Client.ProxyContext proxyContext, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x2682  ret
```
