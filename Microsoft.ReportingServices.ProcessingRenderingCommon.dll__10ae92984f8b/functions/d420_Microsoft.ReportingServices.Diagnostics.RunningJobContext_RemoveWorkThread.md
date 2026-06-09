# Microsoft.ReportingServices.Diagnostics.RunningJobContext::RemoveWorkThread

- ea: `0xd420`
- end: `0xd45f`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobContext::RemoveWorkThread`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x9c50`
- `0xe1c0`

## callees

- `0xd420`
- `0xd600`
- `0xd9a0`
- `0xe0f0`

## pseudocode

```c

```

## disassembly

```asm
0xd420  ldarg.0
0xd421  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_threadsCtx
0xd426  ldarg.1
0xd427  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0xd42c  brfalse.s loc_D440
0xd42e  ldarg.0
0xd42f  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_threadsCtx
0xd434  ldarg.1
0xd435  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0xd43a  ldarg.1
0xd43b  callvirt instance void Microsoft.ReportingServices.Diagnostics.ThreadJobContext::Dispose()
0xd440  ldarg.0
0xd441  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_threadsCtx
0xd446  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd44b  brtrue.s loc_D45E
0xd44d  ldarg.0
0xd44e  ldfld    class Microsoft.ReportingServices.Diagnostics.RunningJobList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_runningJobs
0xd453  ldarg.0
0xd454  call     instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xd459  callvirt instance void Microsoft.ReportingServices.Diagnostics.RunningJobList::RemoveJob(string jobId)
0xd45e  ret
```
