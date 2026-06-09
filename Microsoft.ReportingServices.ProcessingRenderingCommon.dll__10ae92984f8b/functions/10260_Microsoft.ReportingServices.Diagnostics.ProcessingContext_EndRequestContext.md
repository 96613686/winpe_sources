# Microsoft.ReportingServices.Diagnostics.ProcessingContext::EndRequestContext

- ea: `0x10260`
- end: `0x10278`
- name: `Microsoft.ReportingServices.Diagnostics.ProcessingContext::EndRequestContext`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xe500`
- `0xe540`
- `0xe880`

## callees

- `0xb200`
- `0x10200`
- `0x10260`

## pseudocode

```c

```

## disassembly

```asm
0x10260  call     void Microsoft.ReportingServices.Diagnostics.RequestCache::ReleaseReferenceAndDetach()
0x10265  call     class Microsoft.ReportingServices.Diagnostics.RequestContext Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_ReqContext()
0x1026a  brfalse.s loc_10277
0x1026c  ldsfld   class [mscorlib]System.Threading.AsyncLocal`1<class Microsoft.ReportingServices.Diagnostics.RequestContext> Microsoft.ReportingServices.Diagnostics.ProcessingContext::_reqContext
0x10271  ldnull
0x10272  callvirt instance void class [mscorlib]System.Threading.AsyncLocal`1<class Microsoft.ReportingServices.Diagnostics.RequestContext>::set_Value(var<u1>)
0x10277  ret
```
