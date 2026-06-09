# Microsoft.ReportingServices.Library.DBPoll::StopPollingThread

- ea: `0xc40`
- end: `0xc9c`
- name: `Microsoft.ReportingServices.Library.DBPoll::StopPollingThread`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xbd0`
- `0xc40`
- `0xe20`

## string_xrefs

- `0xc73`: `[ThreadAborted] Aborting the polling thread after a 5 second wait.`

## pseudocode

```c

```

## disassembly

```asm
0xc40  ldarg.1
0xc41  unbox.any [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals/ServiceStopMode
0xc46  stloc.0
0xc47  ldarg.0
0xc48  ldc.i4.0
0xc49  stfld    bool Microsoft.ReportingServices.Library.DBPoll::m_continuePolling
0xc4e  call     void Microsoft.ReportingServices.Library.DBPoll::SetWaitEvent()
0xc53  ldarg.0
0xc54  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.DBPoll::m_pollingThread
0xc59  brfalse.s loc_C94
0xc5b  ldarg.0
0xc5c  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.DBPoll::m_pollingThread
0xc61  ldc.i4   0x1388
0xc66  callvirt instance bool [mscorlib]System.Threading.Thread::Join(int32)
0xc6b  brtrue.s loc_C88
0xc6d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0xc72  ldc.i4.3
0xc73  ldstr    aThreadabortedA// "[ThreadAborted] Aborting the polling th"...
0xc78  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xc7d  ldarg.0
0xc7e  ldfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.DBPoll::m_pollingThread
0xc83  callvirt instance void [mscorlib]System.Threading.Thread::Abort()
0xc88  leave.s  loc_C8D
0xc8a  pop
0xc8b  leave.s  loc_C8D
0xc8d  ldarg.0
0xc8e  ldnull
0xc8f  stfld    class [mscorlib]System.Threading.Thread Microsoft.ReportingServices.Library.DBPoll::m_pollingThread
0xc94  ldarg.0
0xc95  ldloc.0
0xc96  call     instance void Microsoft.ReportingServices.Library.DBPoll::StopPollWorkers(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals/ServiceStopMode mode)
0xc9b  ret
```
