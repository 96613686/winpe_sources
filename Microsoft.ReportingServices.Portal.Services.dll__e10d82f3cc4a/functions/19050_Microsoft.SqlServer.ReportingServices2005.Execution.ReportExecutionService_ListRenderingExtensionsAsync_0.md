# Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsAsync_0

- ea: `0x19050`
- end: `0x19083`
- name: `Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsAsync_0`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x19040`

## callees

- `0x19050`

## string_xrefs

- `0x1906b`: `ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x19050  ldarg.0
0x19051  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsOperationCompleted
0x19056  brtrue.s loc_1906A
0x19058  ldarg.0
0x19059  ldarg.0
0x1905a  ldftn    instance void Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::OnListRenderingExtensionsOperationCompleted(object arg)
0x19060  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x19065  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsOperationCompleted
0x1906a  ldarg.0
0x1906b  ldstr    aListrenderinge// "ListRenderingExtensions"
0x19070  ldc.i4.0
0x19071  newarr   [mscorlib]System.Object
0x19076  ldarg.0
0x19077  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsOperationCompleted
0x1907c  ldarg.1
0x1907d  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x19082  ret
```
