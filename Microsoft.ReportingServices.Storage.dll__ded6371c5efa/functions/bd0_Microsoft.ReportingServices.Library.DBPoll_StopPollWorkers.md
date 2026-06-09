# Microsoft.ReportingServices.Library.DBPoll::StopPollWorkers

- ea: `0xbd0`
- end: `0xc31`
- name: `Microsoft.ReportingServices.Library.DBPoll::StopPollWorkers`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xc40`

## callees

- `0xbd0`
- `0xf90`
- `0x11b0`

## pseudocode

```c

```

## disassembly

```asm
0xbd0  ldarg.0
0xbd1  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.DBPoll::m_workers
0xbd6  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0xbdb  stloc.0
0xbdc  ldc.i4.0
0xbdd  stloc.1
0xbde  ldloc.0
0xbdf  ldloca.s 1
0xbe1  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xbe6  ldarg.0
0xbe7  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.DBPoll::m_workers
0xbec  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xbf1  stloc.2
0xbf2  br.s     loc_C05
0xbf4  ldloc.2
0xbf5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xbfa  castclass Microsoft.ReportingServices.Library.PollWorker
0xbff  ldarg.1
0xc00  callvirt instance void Microsoft.ReportingServices.Library.PollWorker::Stop(valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals/ServiceStopMode mode)
0xc05  ldloc.2
0xc06  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc0b  brtrue.s loc_BF4
0xc0d  leave.s  loc_C2A
0xc0f  ldloc.2
0xc10  isinst   [mscorlib]System.IDisposable
0xc15  stloc.3
0xc16  ldloc.3
0xc17  brfalse.s loc_C1F
0xc19  ldloc.3
0xc1a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc1f  endfinally
0xc20  ldloc.1
0xc21  brfalse.s loc_C29
0xc23  ldloc.0
0xc24  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xc29  endfinally
0xc2a  ldarg.0
0xc2b  call     instance void Microsoft.ReportingServices.Library.DBPoll::ClearWorkers()
0xc30  ret
```
