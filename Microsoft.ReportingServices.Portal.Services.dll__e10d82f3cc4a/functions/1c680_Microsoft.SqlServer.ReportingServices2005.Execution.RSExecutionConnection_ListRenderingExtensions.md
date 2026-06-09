# Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::ListRenderingExtensions

- ea: `0x1c680`
- end: `0x1c69f`
- name: `Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::ListRenderingExtensions`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x1c680`: `ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x1c680  ldstr    aListrenderinge// "ListRenderingExtensions"
0x1c685  ldarg.0
0x1c686  ldftn    instance class Microsoft.SqlServer.ReportingServices2005.Execution.Extension[] Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::<ListRenderingExtensions>b__53_0()
0x1c68c  newobj   instance void class ProxyMethodCallback<class Microsoft.SqlServer.ReportingServices2005.Execution.Extension[]>::.ctor(object, native int)
0x1c691  newobj   instance void class ProxyMethod`1<class Microsoft.SqlServer.ReportingServices2005.Execution.Extension[]>::.ctor(string, class ProxyMethodCallback<var<u1>>)
0x1c696  stloc.0
0x1c697  ldarg.0
0x1c698  ldloc.0
0x1c699  call     T0x2B000110
0x1c69e  ret
```
