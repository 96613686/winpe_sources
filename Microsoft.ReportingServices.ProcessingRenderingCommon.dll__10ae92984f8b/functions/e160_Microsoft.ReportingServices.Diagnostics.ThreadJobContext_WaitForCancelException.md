# Microsoft.ReportingServices.Diagnostics.ThreadJobContext::WaitForCancelException

- ea: `0xe160`
- end: `0xe1b3`
- name: `Microsoft.ReportingServices.Diagnostics.ThreadJobContext::WaitForCancelException`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b60`

## callees

- `0xe160`
- `0x10310`

## string_xrefs

- `0xe166`: `ThreadJobContext.WaitForCancelException entered`
- `0xe1a8`: `ThreadJobContext.WaitForCancelException finished`

## pseudocode

```c

```

## disassembly

```asm
0xe160  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe165  ldc.i4.4
0xe166  ldstr    aThreadjobconte_3// "ThreadJobContext.WaitForCancelException"...
0xe16b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe170  ldc.i4.0
0xe171  stloc.0
0xe172  br.s     loc_E199
0xe174  ldloc.0
0xe175  ldc.i4.1
0xe176  add
0xe177  stloc.0
0xe178  ldc.i4.s 0x64
0xe17a  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xe17f  ldloc.0
0xe180  ldc.i4   0x186A0
0xe185  ble.s    loc_E199
0xe187  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe18c  ldc.i4.1
0xe18d  ldstr    aWaitForCancelL// "Wait for cancel lock still on, breaking"...
0xe192  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe197  br.s     loc_E1A2
0xe199  ldarg.0
0xe19a  ldfld    int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::m_state
0xe19f  ldc.i4.2
0xe1a0  beq.s    loc_E174
0xe1a2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe1a7  ldc.i4.4
0xe1a8  ldstr    aThreadjobconte_4// "ThreadJobContext.WaitForCancelException"...
0xe1ad  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe1b2  ret
```
