# Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsAsync_0

- ea: `0x29070`
- end: `0x290a3`
- name: `Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsAsync_0`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x29060`

## callees

- `0x29070`

## string_xrefs

- `0x2908b`: `ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x29070  ldarg.0
0x29071  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsOperationCompleted
0x29076  brtrue.s loc_2908A
0x29078  ldarg.0
0x29079  ldarg.0
0x2907a  ldftn    instance void Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::OnListRenderingExtensionsOperationCompleted(object arg)
0x29080  newobj   instance void [mscorlib]System.Threading.SendOrPostCallback::.ctor(object, native int)
0x29085  stfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsOperationCompleted
0x2908a  ldarg.0
0x2908b  ldstr    aListrenderinge// "ListRenderingExtensions"
0x29090  ldc.i4.0
0x29091  newarr   [mscorlib]System.Object
0x29096  ldarg.0
0x29097  ldfld    class [mscorlib]System.Threading.SendOrPostCallback Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensionsOperationCompleted
0x2909c  ldarg.1
0x2909d  call     instance void [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::InvokeAsync(string, object[], class [mscorlib]System.Threading.SendOrPostCallback, object)
0x290a2  ret
```
