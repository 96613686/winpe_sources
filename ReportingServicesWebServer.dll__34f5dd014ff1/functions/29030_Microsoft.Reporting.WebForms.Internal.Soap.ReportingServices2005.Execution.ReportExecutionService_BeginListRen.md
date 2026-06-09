# Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::BeginListRenderingExtensions

- ea: `0x29030`
- end: `0x29044`
- name: `Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::BeginListRenderingExtensions`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x29031`: `ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x29030  ldarg.0
0x29031  ldstr    aListrenderinge// "ListRenderingExtensions"
0x29036  ldc.i4.0
0x29037  newarr   [mscorlib]System.Object
0x2903c  ldarg.1
0x2903d  ldarg.2
0x2903e  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x29043  ret
```
