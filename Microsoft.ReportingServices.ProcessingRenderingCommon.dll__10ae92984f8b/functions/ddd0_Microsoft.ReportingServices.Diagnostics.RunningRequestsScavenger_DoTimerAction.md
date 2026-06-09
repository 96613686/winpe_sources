# Microsoft.ReportingServices.Diagnostics.RunningRequestsScavenger::DoTimerAction

- ea: `0xddd0`
- end: `0xdec2`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequestsScavenger::DoTimerAction`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0xd460`
- `0xd4a0`
- `0xd510`
- `0xd600`
- `0xd620`
- `0xd7b0`
- `0xd800`
- `0xddd0`
- `0xe940`
- `0x10310`

## pseudocode

```c

```

## disassembly

```asm
0xddd0  call     class Microsoft.ReportingServices.Diagnostics.RunningJobList Microsoft.ReportingServices.Diagnostics.RunningJobList::get_Current()
0xddd5  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobList::CopyTo()
0xddda  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0xdddf  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xdde4  stloc.0
0xdde5  br       loc_DEA3
0xddea  ldloc.0
0xddeb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xddf0  castclass Microsoft.ReportingServices.Diagnostics.RunningJobContext
0xddf5  stloc.1
0xddf6  ldarg.0
0xddf7  call     instance bool Microsoft.ReportingServices.Diagnostics.TimerActionBase::get_ContinueExecuting()
0xddfc  brtrue.s loc_DE03
0xddfe  leave    loc_DEC1
0xde03  ldloc.1
0xde04  callvirt instance bool Microsoft.ReportingServices.Diagnostics.RunningJobContext::IsClientConnected()
0xde09  brtrue.s loc_DE3E
0xde0b  ldloc.1
0xde0c  ldc.i4.2
0xde0d  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.RunningJobContext::Cancel(valuetype AbortReason reason)
0xde12  brtrue.s loc_DE77
0xde14  ldloc.1
0xde15  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Status()
0xde1a  ldc.i4.2
0xde1b  beq.s    loc_DE77
0xde1d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xde22  ldc.i4.2
0xde23  ldstr    aRunningjobcont_2// "RunningJobContext.Cancel(JobOrphaned) f"...
0xde28  ldc.i4.1
0xde29  newarr   [mscorlib]System.Object
0xde2e  dup
0xde2f  ldc.i4.0
0xde30  ldloc.1
0xde31  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xde36  stelem.ref
0xde37  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xde3c  br.s     loc_DE77
0xde3e  ldloc.1
0xde3f  callvirt instance bool Microsoft.ReportingServices.Diagnostics.RunningJobContext::IsExpired()
0xde44  brfalse.s loc_DE77
0xde46  ldloc.1
0xde47  ldc.i4.0
0xde48  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.RunningJobContext::Cancel(valuetype AbortReason reason)
0xde4d  brtrue.s loc_DE77
0xde4f  ldloc.1
0xde50  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Status()
0xde55  ldc.i4.2
0xde56  beq.s    loc_DE77
0xde58  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xde5d  ldc.i4.2
0xde5e  ldstr    aRunningjobcont_3// "RunningJobContext.Cancel(TimeoutExpired"...
0xde63  ldc.i4.1
0xde64  newarr   [mscorlib]System.Object
0xde69  dup
0xde6a  ldc.i4.0
0xde6b  ldloc.1
0xde6c  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xde71  stelem.ref
0xde72  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xde77  leave.s  loc_DEA3
0xde79  stloc.2
0xde7a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xde7f  ldc.i4.1
0xde80  ldstr    aExceptionInRun// "Exception in RunningRequestsScavenger.D"...
0xde85  ldc.i4.1
0xde86  newarr   [mscorlib]System.Object
0xde8b  dup
0xde8c  ldc.i4.0
0xde8d  ldloc.2
0xde8e  stelem.ref
0xde8f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xde94  ldloc.2
0xde95  isinst   [mscorlib]System.Threading.ThreadAbortException
0xde9a  brfalse.s loc_DEA1
0xde9c  call     void [mscorlib]System.Threading.Thread::ResetAbort()
0xdea1  leave.s  loc_DEA3
0xdea3  ldloc.0
0xdea4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xdea9  brtrue   loc_DDEA
0xdeae  leave.s  loc_DEC1
0xdeb0  ldloc.0
0xdeb1  isinst   [mscorlib]System.IDisposable
0xdeb6  stloc.3
0xdeb7  ldloc.3
0xdeb8  brfalse.s loc_DEC0
0xdeba  ldloc.3
0xdebb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdec0  endfinally
0xdec1  ret
```
