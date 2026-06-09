# Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::BeginListRenderingExtensions

- ea: `0x19010`
- end: `0x19024`
- name: `Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::BeginListRenderingExtensions`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x19011`: `ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x19010  ldarg.0
0x19011  ldstr    aListrenderinge// "ListRenderingExtensions"
0x19016  ldc.i4.0
0x19017  newarr   [mscorlib]System.Object
0x1901c  ldarg.1
0x1901d  ldarg.2
0x1901e  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x19023  ret
```
