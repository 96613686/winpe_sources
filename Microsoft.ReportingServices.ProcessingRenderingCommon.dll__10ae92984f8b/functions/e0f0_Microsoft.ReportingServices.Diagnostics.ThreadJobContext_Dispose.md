# Microsoft.ReportingServices.Diagnostics.ThreadJobContext::Dispose

- ea: `0xe0f0`
- end: `0xe11c`
- name: `Microsoft.ReportingServices.Diagnostics.ThreadJobContext::Dispose`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xd420`

## callees

- `0xe0f0`
- `0x101f0`
- `0x10310`

## string_xrefs

- `0xe0fe`: `ThreadJobContext.Dispose object is already disposed`

## pseudocode

```c

```

## disassembly

```asm
0xe0f0  ldarg.0
0xe0f1  ldfld    bool Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_disposed
0xe0f6  brfalse.s loc_E109
0xe0f8  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe0fd  ldc.i4.2
0xe0fe  ldstr    aThreadjobconte_0// "ThreadJobContext.Dispose object is alre"...
0xe103  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe108  ret
0xe109  ldarg.0
0xe10a  ldfld    class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_prevCtx
0xe10f  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::set_ThreadContext(class Microsoft.ReportingServices.Diagnostics.ThreadJobContext value)
0xe114  ldarg.0
0xe115  ldc.i4.1
0xe116  stfld    bool Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_disposed
0xe11b  ret
```
