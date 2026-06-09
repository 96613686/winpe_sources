# Microsoft.ReportingServices.Diagnostics.ThreadJobContext::EndCancelableState

- ea: `0xe140`
- end: `0xe15f`
- name: `Microsoft.ReportingServices.Diagnostics.ThreadJobContext::EndCancelableState`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b60`

## callees

- `0x10310`

## string_xrefs

- `0xe146`: `ThreadJobContext.EndCancelableState`

## pseudocode

```c

```

## disassembly

```asm
0xe140  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe145  ldc.i4.4
0xe146  ldstr    aThreadjobconte_2// "ThreadJobContext.EndCancelableState"
0xe14b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe150  ldarg.0
0xe151  ldflda   int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_state
0xe156  ldc.i4.0
0xe157  ldc.i4.1
0xe158  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xe15d  pop
0xe15e  ret
```
