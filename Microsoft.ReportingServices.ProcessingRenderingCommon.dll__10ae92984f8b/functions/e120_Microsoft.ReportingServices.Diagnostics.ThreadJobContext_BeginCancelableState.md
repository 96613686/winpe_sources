# Microsoft.ReportingServices.Diagnostics.ThreadJobContext::BeginCancelableState

- ea: `0xe120`
- end: `0xe138`
- name: `Microsoft.ReportingServices.Diagnostics.ThreadJobContext::BeginCancelableState`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b60`

## callees

- `0x10310`

## string_xrefs

- `0xe126`: `ThreadJobContext.BeginCancelableState`

## pseudocode

```c

```

## disassembly

```asm
0xe120  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe125  ldc.i4.4
0xe126  ldstr    aThreadjobconte_1// "ThreadJobContext.BeginCancelableState"
0xe12b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe130  ldarg.0
0xe131  ldc.i4.1
0xe132  stfld    int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_state
0xe137  ret
```
