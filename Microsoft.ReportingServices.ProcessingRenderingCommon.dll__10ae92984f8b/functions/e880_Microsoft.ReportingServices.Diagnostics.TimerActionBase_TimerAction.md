# Microsoft.ReportingServices.Diagnostics.TimerActionBase::TimerAction

- ea: `0xe880`
- end: `0xe935`
- name: `Microsoft.ReportingServices.Diagnostics.TimerActionBase::TimerAction`
- size: `181`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x9910`
- `0xe880`
- `0xe9a0`
- `0x10230`
- `0x10260`
- `0x10310`

## pseudocode

```c

```

## disassembly

```asm
0xe880  ldarg.0
0xe881  ldflda   int32 Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_timerExecutingLock
0xe886  ldc.i4.1
0xe887  ldc.i4.0
0xe888  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xe88d  brfalse.s loc_E8BC
0xe88f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe894  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0xe899  brfalse.s loc_E8BB
0xe89b  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe8a0  ldc.i4.2
0xe8a1  ldstr    aPreviousReques// "Previous request for "
0xe8a6  ldarg.0
0xe8a7  ldfld    string Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_timerTypeForTrace
0xe8ac  ldstr    aStillExecuting_0// "still executing, skipping..."
0xe8b1  call     string [mscorlib]System.String::Concat(string, string, string)
0xe8b6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe8bb  ret
0xe8bc  ldarg.0
0xe8bd  ldfld    class Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_serviceInstanceContext
0xe8c2  newobj   instance void Microsoft.ReportingServices.Diagnostics.BackgroundRequestContext::.ctor(class Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext serviceInstanceContext)
0xe8c7  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::InitializeRequestContext(class Microsoft.ReportingServices.Diagnostics.RequestContext context)
0xe8cc  ldarg.0
0xe8cd  callvirt instance void Microsoft.ReportingServices.Diagnostics.TimerActionBase::DoTimerAction()
0xe8d2  leave.s  loc_E934
0xe8d4  stloc.0
0xe8d5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe8da  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0xe8df  brfalse.s loc_E907
0xe8e1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe8e6  ldc.i4.1
0xe8e7  ldstr    aErrorInTimer// "Error in timer "
0xe8ec  ldarg.0
0xe8ed  ldfld    string Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_timerTypeForTrace
0xe8f2  ldstr    asc_217EE// " : "
0xe8f7  ldloc.0
0xe8f8  callvirt instance string [mscorlib]System.Object::ToString()
0xe8fd  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xe902  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe907  leave.s  loc_E934
0xe909  ldstr    aUnhandledExcep// "Unhandled exception in timer "
0xe90e  ldarg.0
0xe90f  ldfld    string Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_timerTypeForTrace
0xe914  call     string [mscorlib]System.String::Concat(string, string)
0xe919  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0xe91e  pop
0xe91f  leave.s  loc_E934
0xe921  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::EndRequestContext()
0xe926  ldarg.0
0xe927  ldflda   int32 Microsoft.ReportingServices.Diagnostics.TimerActionBase::m_timerExecutingLock
0xe92c  ldc.i4.0
0xe92d  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0xe932  pop
0xe933  endfinally
0xe934  ret
```
