# Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.RSExecutionConnection::ListRenderingExtensions

- ea: `0x25c50`
- end: `0x25c6f`
- name: `Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.RSExecutionConnection::ListRenderingExtensions`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## string_xrefs

- `0x25c50`: `ListRenderingExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x25c50  ldstr    aListrenderinge// "ListRenderingExtensions"
0x25c55  ldarg.0
0x25c56  ldftn    instance class Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.Extension[] Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.RSExecutionConnection::<ListRenderingExtensions>b__53_0()
0x25c5c  newobj   instance void class ProxyMethodCallback<class Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.Extension[]>::.ctor(object, native int)
0x25c61  newobj   instance void class ProxyMethod`1<class Microsoft.Reporting.WebForms.Internal.Soap.ReportingServices2005.Execution.Extension[]>::.ctor(string, class ProxyMethodCallback<var<u1>>)
0x25c66  stloc.0
0x25c67  ldarg.0
0x25c68  ldloc.0
0x25c69  call     T0x2B00003B
0x25c6e  ret
```
