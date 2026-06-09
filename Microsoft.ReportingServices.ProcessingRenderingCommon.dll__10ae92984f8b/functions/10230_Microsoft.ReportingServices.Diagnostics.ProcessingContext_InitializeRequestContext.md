# Microsoft.ReportingServices.Diagnostics.ProcessingContext::InitializeRequestContext

- ea: `0x10230`
- end: `0x1025f`
- name: `Microsoft.ReportingServices.Diagnostics.ProcessingContext::InitializeRequestContext`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xe500`
- `0xe540`
- `0xe880`

## callees

- `0xb1b0`
- `0xb7f0`
- `0x10080`

## pseudocode

```c

```

## disassembly

```asm
0x10230  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RunningJobsTrace()
0x10235  ldarg.0
0x10236  ldnull
0x10237  cgt.un
0x10239  ldstr    aContextNull// "context != null"
0x1023e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x10243  ldsfld   class [mscorlib]System.Threading.AsyncLocal`1<class Microsoft.ReportingServices.Diagnostics.RequestContext> Microsoft.ReportingServices.Diagnostics.ProcessingContext::_reqContext
0x10248  ldarg.0
0x10249  callvirt instance void class [mscorlib]System.Threading.AsyncLocal`1<class Microsoft.ReportingServices.Diagnostics.RequestContext>::set_Value(var<u1>)
0x1024e  ldarg.0
0x1024f  callvirt instance class Microsoft.ReportingServices.Diagnostics.Timer Microsoft.ReportingServices.Diagnostics.RequestContextBase::get_RequestTimer()
0x10254  callvirt instance void Microsoft.ReportingServices.Diagnostics.Timer::StartTimer()
0x10259  call     void Microsoft.ReportingServices.Diagnostics.RequestCache::InitializeForRequest()
0x1025e  ret
```
