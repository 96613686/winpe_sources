# Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext

- ea: `0x10200`
- end: `0x1020b`
- name: `Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext`
- size: `11`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a70`
- `0x46a0`
- `0x9a30`
- `0x9f10`
- `0x10260`
- `0x10280`
- `0x15b90`
- `0x16310`

## pseudocode

```c

```

## disassembly

```asm
0x10200  ldsfld   class [mscorlib]System.Threading.AsyncLocal`1<class Microsoft.ReportingServices.Diagnostics.RequestContext> Microsoft.ReportingServices.Diagnostics.ProcessingContext::_reqContext
0x10205  callvirt instance var<u1> class [mscorlib]System.Threading.AsyncLocal`1<class Microsoft.ReportingServices.Diagnostics.RequestContext>::get_Value()
0x1020a  ret
```
