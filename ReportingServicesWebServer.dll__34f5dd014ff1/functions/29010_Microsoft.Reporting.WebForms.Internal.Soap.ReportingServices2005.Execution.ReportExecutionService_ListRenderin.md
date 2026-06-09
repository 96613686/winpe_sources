# Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensions

- ea: `0x29010`
- end: `0x29029`
- name: `Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensions`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x25d40`

## callees

- `0x26cd0`

## string_xrefs

- `0x29011`: `ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x29010  ldarg.0
0x29011  ldstr    aListrenderinge// "ListRenderingExtensions"
0x29016  ldc.i4.0
0x29017  newarr   [mscorlib]System.Object
0x2901c  call     instance object[] Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.ReportExecutionService::Invoke(string methodName, object[] parameters)
0x29021  ldc.i4.0
0x29022  ldelem.ref
0x29023  castclass class Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.Extension[]
0x29028  ret
```
