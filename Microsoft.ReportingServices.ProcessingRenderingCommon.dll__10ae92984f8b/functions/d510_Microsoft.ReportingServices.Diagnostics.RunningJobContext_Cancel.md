# Microsoft.ReportingServices.Diagnostics.RunningJobContext::Cancel

- ea: `0xd510`
- end: `0xd5f3`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobContext::Cancel`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xdad0`
- `0xddd0`

## callees

- `0xd510`
- `0xd600`
- `0xd610`
- `0xdf90`
- `0xe1c0`
- `0x10310`

## string_xrefs

- `0xd532`: `RunningJobContext.Cancel; Skipping -- Cancel has been requested already`
- `0xd58e`: `ThreadJobContext.Cancel({0}) failed for job {1} and thread {2}`

## pseudocode

```c

```

## disassembly

```asm
0xd510  ldc.i4.0
0xd511  stloc.0
0xd512  ldarg.0
0xd513  call     instance object Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_StatusSyncRoot()
0xd518  stloc.1
0xd519  ldc.i4.0
0xd51a  stloc.2
0xd51b  ldloc.1
0xd51c  ldloca.s 2
0xd51e  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xd523  ldarg.0
0xd524  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_status
0xd529  ldc.i4.2
0xd52a  bne.un.s loc_D543
0xd52c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xd531  ldc.i4.4
0xd532  ldstr    aRunningjobcont_1// "RunningJobContext.Cancel; Skipping -- C"...
0xd537  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xd53c  ldloc.0
0xd53d  stloc.3
0xd53e  leave    loc_D5F1
0xd543  ldarg.0
0xd544  ldc.i4.2
0xd545  stfld    valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_status
0xd54a  leave.s  loc_D556
0xd54c  ldloc.2
0xd54d  brfalse.s loc_D555
0xd54f  ldloc.1
0xd550  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xd555  endfinally
0xd556  ldarg.0
0xd557  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_threadsCtx
0xd55c  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(class [mscorlib]System.Collections.ICollection)
0xd561  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xd566  stloc.s  4
0xd568  br.s     loc_D5CF
0xd56a  ldloc.s  4
0xd56c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xd571  castclass Microsoft.ReportingServices.Diagnostics.ThreadJobContext
0xd576  stloc.s  5
0xd578  ldloc.s  5
0xd57a  ldarg.1
0xd57b  callvirt instance bool Microsoft.ReportingServices.Diagnostics.ThreadJobContext::Cancel(valuetype AbortReason reason)
0xd580  brfalse.s loc_D588
0xd582  ldloc.0
0xd583  ldc.i4.1
0xd584  add
0xd585  stloc.0
0xd586  br.s     loc_D5CF
0xd588  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xd58d  ldc.i4.2
0xd58e  ldstr    aThreadjobconte// "ThreadJobContext.Cancel({0}) failed for"...
0xd593  ldc.i4.3
0xd594  newarr   [mscorlib]System.Object
0xd599  dup
0xd59a  ldc.i4.0
0xd59b  ldarga.s 1
0xd59d  constrained. AbortReason
0xd5a3  callvirt instance string [mscorlib]System.Object::ToString()
0xd5a8  stelem.ref
0xd5a9  dup
0xd5aa  ldc.i4.1
0xd5ab  ldarg.0
0xd5ac  call     instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xd5b1  stelem.ref
0xd5b2  dup
0xd5b3  ldc.i4.2
0xd5b4  ldloc.s  5
0xd5b6  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.ThreadJobContext::get_ThreadId()
0xd5bb  stloc.s  6
0xd5bd  ldloca.s 6
0xd5bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd5c4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xd5c9  stelem.ref
0xd5ca  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xd5cf  ldloc.s  4
0xd5d1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd5d6  brtrue.s loc_D56A
0xd5d8  leave.s  loc_D5EF
0xd5da  ldloc.s  4
0xd5dc  isinst   [mscorlib]System.IDisposable
0xd5e1  stloc.s  7
0xd5e3  ldloc.s  7
0xd5e5  brfalse.s loc_D5EE
0xd5e7  ldloc.s  7
0xd5e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd5ee  endfinally
0xd5ef  ldloc.0
0xd5f0  ret
0xd5f1  ldloc.3
0xd5f2  ret
```
