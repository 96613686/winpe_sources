# Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensions

- ea: `0x18ff0`
- end: `0x19009`
- name: `Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::ListRenderingExtensions`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1c770`

## callees

- `0x16cb0`

## string_xrefs

- `0x18ff1`: `ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x18ff0  ldarg.0
0x18ff1  ldstr    aListrenderinge// "ListRenderingExtensions"
0x18ff6  ldc.i4.0
0x18ff7  newarr   [mscorlib]System.Object
0x18ffc  call     instance object[] Microsoft.SqlServer.ReportingServices2005.Execution.ReportExecutionService::Invoke(string methodName, object[] parameters)
0x19001  ldc.i4.0
0x19002  ldelem.ref
0x19003  castclass class Microsoft.SqlServer.ReportingServices2005.Execution.Extension[]
0x19008  ret
```
