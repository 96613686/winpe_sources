# Microsoft.SharePoint.Client.ClientRequestService::ProcessRestQuery

- ea: `0x69f0`
- end: `0x6aed`
- name: `Microsoft.SharePoint.Client.ClientRequestService::ProcessRestQuery`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x6700`
- `0x6820`
- `0x69f0`
- `0x6b30`
- `0xe000`
- `0xe0f0`
- `0xe620`
- `0xeb70`
- `0xebb0`
- `0xebe0`
- `0xec80`
- `0x12eb0`
- `0x279d0`

## string_xrefs

- `0x6a3f`: `ClientRequestService.ProcessRestQuery`

## pseudocode

```c

```

## disassembly

```asm
0x69f0  call     void Microsoft.SharePoint.Client.ClientServiceOperationContext::InitCurrent()
0x69f5  call     class Microsoft.SharePoint.Client.ClientServiceOperationContext Microsoft.SharePoint.Client.ClientServiceOperationContext::get_Current()
0x69fa  ldc.i4.0
0x69fb  callvirt instance void Microsoft.SharePoint.Client.ClientServiceOperationContext::set_RequireFormDigestValidationOnHttpGet(bool value)
0x6a00  call     class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ClientServiceHost::CreateServiceHost()
0x6a05  stloc.0
0x6a06  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Client.ClientRequestService::RequestPerfTraceKillSwitchId
0x6a0b  ldstr    a07172017// "07/17/2017"
0x6a10  ldstr    aRequestperftra// "RequestPerfTrace"
0x6a15  call     bool [Microsoft.SharePoint.KillSwitch]Microsoft.SharePoint.Internal.KillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x6a1a  stloc.1
0x6a1b  ldnull
0x6a1c  stloc.2
0x6a1d  ldloc.1
0x6a1e  brtrue.s loc_6A3B
0x6a20  ldc.i4   0x2736
0x6a25  ldstr    aProcessrestque// "ProcessRestQuery"
0x6a2a  ldstr    aDDbsElZltDevSt// "d:\\dbs\\el\\zlt\\dev\\sts\\Client\\Ser"...
0x6a2f  ldc.i4   0x1A3
0x6a34  call     class [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer::Create(valuetype [Microsoft.Cobalt.Base]Cobalt.ComponentId, string, string, int32)
0x6a39  br.s     loc_6A3C
0x6a3b  ldnull
0x6a3c  stloc.s  5
0x6a3e  ldloc.0
0x6a3f  ldstr    aClientrequests_0// "ClientRequestService.ProcessRestQuery"
0x6a44  ldc.i4.2
0x6a45  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(string name, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x6a4a  stloc.s  6
0x6a4c  ldloc.0
0x6a4d  call     valuetype Microsoft.SharePoint.Client.ODataProtocolVersion Microsoft.SharePoint.Client.ClientRequestService::GetRequestODataProtocolVersion(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x6a52  stloc.3
0x6a53  ldloc.3
0x6a54  ldc.i4.2
0x6a55  bne.un.s loc_6A6A
0x6a57  ldloc.0
0x6a58  ldc.i4   0x65C848
0x6a5d  ldc.i4.3
0x6a5e  ldstr    aOdata4Request// "OData4 request"
0x6a63  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x6a68  br.s     loc_6A7B
0x6a6a  ldloc.0
0x6a6b  ldc.i4   0x65C849
0x6a70  ldc.i4.3
0x6a71  ldstr    aOdata3Request// "OData3 request"
0x6a76  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x6a7b  ldloc.3
0x6a7c  ldc.i4.2
0x6a7d  bne.un.s loc_6AA4
0x6a7f  ldloc.0
0x6a80  ldc.i4   0x6407DA
0x6a85  ldc.i4.3
0x6a86  ldstr    aOdata4RequestA// "OData4 Request and OData4 is enabled"
0x6a8b  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x6a90  ldloc.0
0x6a91  call     class [mscorlib]System.Type Microsoft.SharePoint.Client.ClientRequestService::GetOData4RestServiceType(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x6a96  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x6a9b  castclass Microsoft.SharePoint.Client.IRESTfulService
0x6aa0  stloc.s  4
0x6aa2  br.s     loc_6AAB
0x6aa4  newobj   instance void Microsoft.SharePoint.Client.Rest.RestService::.ctor()
0x6aa9  stloc.s  4
0x6aab  ldloc.s  4
0x6aad  ldloc.0
0x6aae  ldarg.1
0x6aaf  call     class Microsoft.SharePoint.Client.ClientServiceOperationContext Microsoft.SharePoint.Client.ClientServiceOperationContext::get_Current()
0x6ab4  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.IDisposable> Microsoft.SharePoint.Client.ClientServiceOperationContext::get_PendingDisposableObjects()
0x6ab9  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.IRESTfulService::ProcessQuery(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class [mscorlib]System.IO.Stream inputStream, class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.IDisposable> pendingDisposableContainer)
0x6abe  stloc.2
0x6abf  leave.s  loc_6ACD
0x6ac1  ldloc.s  6
0x6ac3  brfalse.s loc_6ACC
0x6ac5  ldloc.s  6
0x6ac7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6acc  endfinally
0x6acd  leave.s  loc_6ADB
0x6acf  ldloc.s  5
0x6ad1  brfalse.s loc_6ADA
0x6ad3  ldloc.s  5
0x6ad5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ada  endfinally
0x6adb  ldloc.1
0x6adc  brtrue.s loc_6AEB
0x6ade  ldloc.2
0x6adf  brtrue.s loc_6AE3
0x6ae1  ldnull
0x6ae2  ret
0x6ae3  ldloc.2
0x6ae4  ldloc.0
0x6ae5  newobj   instance void StreamWrapperForPerfTracing::.ctor(class [mscorlib]System.IO.Stream stream, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x6aea  ret
0x6aeb  ldloc.2
0x6aec  ret
```
