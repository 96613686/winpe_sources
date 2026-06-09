# Microsoft.ReportingServices.Library.DBPoll::StartPollWorkers

- ea: `0xb00`
- end: `0xb69`
- name: `Microsoft.ReportingServices.Library.DBPoll::StartPollWorkers`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xb70`

## callees

- `0xb00`
- `0x1150`

## pseudocode

```c

```

## disassembly

```asm
0xb00  ldarg.0
0xb01  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.DBPoll::m_workers
0xb06  callvirt instance object [mscorlib]System.Collections.ArrayList::get_SyncRoot()
0xb0b  stloc.0
0xb0c  ldc.i4.0
0xb0d  stloc.1
0xb0e  ldloc.0
0xb0f  ldloca.s 1
0xb11  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xb16  ldarg.0
0xb17  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.DBPoll::m_workers
0xb1c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xb21  brtrue.s loc_B25
0xb23  leave.s  loc_B68
0xb25  ldarg.0
0xb26  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.DBPoll::m_workers
0xb2b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xb30  stloc.2
0xb31  br.s     loc_B43
0xb33  ldloc.2
0xb34  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xb39  castclass Microsoft.ReportingServices.Library.PollWorker
0xb3e  callvirt instance void Microsoft.ReportingServices.Library.PollWorker::Start()
0xb43  ldloc.2
0xb44  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb49  brtrue.s loc_B33
0xb4b  leave.s  loc_B68
0xb4d  ldloc.2
0xb4e  isinst   [mscorlib]System.IDisposable
0xb53  stloc.3
0xb54  ldloc.3
0xb55  brfalse.s loc_B5D
0xb57  ldloc.3
0xb58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb5d  endfinally
0xb5e  ldloc.1
0xb5f  brfalse.s loc_B67
0xb61  ldloc.0
0xb62  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xb67  endfinally
0xb68  ret
```
