# Microsoft.ReportingServices.Diagnostics.TimerActionBase::Update

- ea: `0xe780`
- end: `0xe80f`
- name: `Microsoft.ReportingServices.Diagnostics.TimerActionBase::Update`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xddb0`

## callees

- `0xe780`
- `0x10310`

## string_xrefs

- `0xe794`: `Timer is updated: Next Event:{0} seconds. Cycle: {1} seconds`
- `0xe7bf`: `Timer {0} is disposed. Update was unsuccessful`
- `0xe7e1`: `Timer {0} configuration out of range: Next Event: {1} seconds. Cycle: {2} seconds`

## pseudocode

```c

```

## disassembly

```asm
0xe780  ldarg.0
0xe781  ldfld    class [mscorlib]System.Threading.Timer Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_timer
0xe786  ldarg.1
0xe787  ldarg.2
0xe788  callvirt instance bool [mscorlib]System.Threading.Timer::Change(int32, int32)
0xe78d  pop
0xe78e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe793  ldc.i4.3
0xe794  ldstr    aTimerIsUpdated// "Timer is updated: Next Event:{0} second"...
0xe799  ldc.i4.2
0xe79a  newarr   [mscorlib]System.Object
0xe79f  dup
0xe7a0  ldc.i4.0
0xe7a1  ldarg.1
0xe7a2  box      [mscorlib]System.Int32
0xe7a7  stelem.ref
0xe7a8  dup
0xe7a9  ldc.i4.1
0xe7aa  ldarg.2
0xe7ab  box      [mscorlib]System.Int32
0xe7b0  stelem.ref
0xe7b1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xe7b6  leave.s  loc_E80E
0xe7b8  pop
0xe7b9  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe7be  ldc.i4.1
0xe7bf  ldstr    aTimer0IsDispos// "Timer {0} is disposed. Update was unsuc"...
0xe7c4  ldc.i4.1
0xe7c5  newarr   [mscorlib]System.Object
0xe7ca  dup
0xe7cb  ldc.i4.0
0xe7cc  ldarg.0
0xe7cd  ldfld    string Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_timerTypeForTrace
0xe7d2  stelem.ref
0xe7d3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xe7d8  leave.s  loc_E80E
0xe7da  pop
0xe7db  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe7e0  ldc.i4.1
0xe7e1  ldstr    aTimer0Configur// "Timer {0} configuration out of range: N"...
0xe7e6  ldc.i4.3
0xe7e7  newarr   [mscorlib]System.Object
0xe7ec  dup
0xe7ed  ldc.i4.0
0xe7ee  ldarg.0
0xe7ef  ldfld    string Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_timerTypeForTrace
0xe7f4  stelem.ref
0xe7f5  dup
0xe7f6  ldc.i4.1
0xe7f7  ldarg.1
0xe7f8  box      [mscorlib]System.Int32
0xe7fd  stelem.ref
0xe7fe  dup
0xe7ff  ldc.i4.2
0xe800  ldarg.2
0xe801  box      [mscorlib]System.Int32
0xe806  stelem.ref
0xe807  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xe80c  leave.s  loc_E80E
0xe80e  ret
```
