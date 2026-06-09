# Microsoft.ReportingServices.Diagnostics.RunningJobList::MarkOlderJobs

- ea: `0xd820`
- end: `0xd8ec`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobList::MarkOlderJobs`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0xd600`
- `0xd610`
- `0xd620`
- `0xd630`
- `0xd660`
- `0xd7e0`
- `0xd820`

## pseudocode

```c

```

## disassembly

```asm
0xd820  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xd825  stloc.0
0xd826  ldarg.0
0xd827  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobList::m_runningJobs
0xd82c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_SyncRoot()
0xd831  stloc.1
0xd832  ldc.i4.0
0xd833  stloc.2
0xd834  ldloc.1
0xd835  ldloca.s 2
0xd837  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xd83c  ldarg.0
0xd83d  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobList::m_runningJobs
0xd842  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0xd847  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xd84c  stloc.3
0xd84d  br.s     loc_D8C2
0xd84f  ldloc.3
0xd850  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd855  castclass Microsoft.ReportingServices.Diagnostics.RunningJobContext
0xd85a  stloc.s  4
0xd85c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xd861  ldloc.s  4
0xd863  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_StartDate()
0xd868  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xd86d  stloc.s  5
0xd86f  ldloca.s 5
0xd871  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xd876  ldarg.0
0xd877  call     instance int32 Microsoft.ReportingServices.Diagnostics.RunningJobList::get_SecondsBeforeSave()
0xd87c  conv.r8
0xd87d  blt.s    loc_D8C2
0xd87f  ldloc.s  4
0xd881  callvirt instance object Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_StatusSyncRoot()
0xd886  stloc.s  6
0xd888  ldc.i4.0
0xd889  stloc.s  7
0xd88b  ldloc.s  6
0xd88d  ldloca.s 7
0xd88f  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xd894  ldloc.s  4
0xd896  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Status()
0xd89b  brtrue.s loc_D8A5
0xd89d  ldloc.s  4
0xd89f  ldc.i4.1
0xd8a0  callvirt instance void Microsoft.ReportingServices.Diagnostics.RunningJobContext::set_Status(valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum value)
0xd8a5  leave.s  loc_D8B3
0xd8a7  ldloc.s  7
0xd8a9  brfalse.s loc_D8B2
0xd8ab  ldloc.s  6
0xd8ad  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xd8b2  endfinally
0xd8b3  ldloc.0
0xd8b4  ldloc.s  4
0xd8b6  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xd8bb  ldloc.s  4
0xd8bd  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xd8c2  ldloc.3
0xd8c3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd8c8  brtrue.s loc_D84F
0xd8ca  leave.s  loc_D8EA
0xd8cc  ldloc.3
0xd8cd  isinst   [mscorlib]System.IDisposable
0xd8d2  stloc.s  8
0xd8d4  ldloc.s  8
0xd8d6  brfalse.s loc_D8DF
0xd8d8  ldloc.s  8
0xd8da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd8df  endfinally
0xd8e0  ldloc.2
0xd8e1  brfalse.s loc_D8E9
0xd8e3  ldloc.1
0xd8e4  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xd8e9  endfinally
0xd8ea  ldloc.0
0xd8eb  ret
```
