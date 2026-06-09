# Microsoft.ReportingServices.Diagnostics.RunningJobList::RemoveJob

- ea: `0xd9a0`
- end: `0xda4e`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobList::RemoveJob`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0xd420`

## callees

- `0xd620`
- `0xd9a0`
- `0x10310`
- `0x15ea0`

## string_xrefs

- `0xda04`: `RunningJobList.RemoveJob: `
- `0xda0a`: ` was removed`
- `0xda3d`: `RunningJobList.RemoveJob; Could not find job id to remove. Id=`

## pseudocode

```c

```

## disassembly

```asm
0xd9a0  ldc.i4.1
0xd9a1  stloc.0
0xd9a2  ldc.i4.0
0xd9a3  stloc.1
0xd9a4  ldarg.0
0xd9a5  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobList::m_runningJobs
0xd9aa  callvirt instance object [mscorlib]System.Collections.Hashtable::get_SyncRoot()
0xd9af  stloc.2
0xd9b0  ldc.i4.0
0xd9b1  stloc.3
0xd9b2  ldloc.2
0xd9b3  ldloca.s 3
0xd9b5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xd9ba  ldarg.0
0xd9bb  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobList::m_runningJobs
0xd9c0  ldarg.1
0xd9c1  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0xd9c6  brfalse.s loc_D9ED
0xd9c8  ldarg.0
0xd9c9  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobList::m_runningJobs
0xd9ce  ldarg.1
0xd9cf  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xd9d4  castclass Microsoft.ReportingServices.Diagnostics.RunningJobContext
0xd9d9  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Status()
0xd9de  stloc.1
0xd9df  ldarg.0
0xd9e0  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobList::m_runningJobs
0xd9e5  ldarg.1
0xd9e6  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0xd9eb  leave.s  loc_D9FB
0xd9ed  ldc.i4.0
0xd9ee  stloc.0
0xd9ef  leave.s  loc_D9FB
0xd9f1  ldloc.3
0xd9f2  brfalse.s loc_D9FA
0xd9f4  ldloc.2
0xd9f5  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xd9fa  endfinally
0xd9fb  ldloc.0
0xd9fc  brfalse.s loc_DA37
0xd9fe  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xda03  ldc.i4.4
0xda04  ldstr    aRunningjoblist// "RunningJobList.RemoveJob: "
0xda09  ldarg.1
0xda0a  ldstr    aWasRemoved// " was removed"
0xda0f  call     string [mscorlib]System.String::Concat(string, string, string)
0xda14  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xda19  ldloc.1
0xda1a  ldc.i4.1
0xda1b  beq.s    loc_DA21
0xda1d  ldloc.1
0xda1e  ldc.i4.2
0xda1f  bne.un.s loc_DA4D
0xda21  ldarg.0
0xda22  ldfld    class RemoveRunningJobsDelegate Microsoft.ReportingServices.Diagnostics.RunningJobList::m_RemoveRunningJobsDelegate
0xda27  brfalse.s loc_DA4D
0xda29  ldarg.0
0xda2a  ldfld    class RemoveRunningJobsDelegate Microsoft.ReportingServices.Diagnostics.RunningJobList::m_RemoveRunningJobsDelegate
0xda2f  ldarg.1
0xda30  callvirt instance int32 RemoveRunningJobsDelegate::Invoke(string jobId)
0xda35  pop
0xda36  ret
0xda37  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xda3c  ldc.i4.4
0xda3d  ldstr    aRunningjoblist_0// "RunningJobList.RemoveJob; Could not fin"...
0xda42  ldarg.1
0xda43  call     string [mscorlib]System.String::Concat(string, string)
0xda48  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xda4d  ret
```
