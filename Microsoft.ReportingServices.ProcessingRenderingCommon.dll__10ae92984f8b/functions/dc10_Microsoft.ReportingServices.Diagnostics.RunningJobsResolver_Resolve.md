# Microsoft.ReportingServices.Diagnostics.RunningJobsResolver::Resolve

- ea: `0xdc10`
- end: `0xdd7b`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobsResolver::Resolve`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xdbb0`

## callees

- `0xd600`
- `0xd620`
- `0xdc10`
- `0x10310`

## string_xrefs

- `0xdd45`: `RunningJobsResolver.Resolve: job: {0} was added to the DB_to_remove list`

## pseudocode

```c

```

## disassembly

```asm
0xdc10  ldarg.1
0xdc11  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0xdc16  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xdc1b  stloc.0
0xdc1c  br       loc_DCDE
0xdc21  ldloc.0
0xdc22  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xdc27  castclass Microsoft.ReportingServices.Diagnostics.RunningJobContext
0xdc2c  stloc.1
0xdc2d  ldarg.2
0xdc2e  ldloc.1
0xdc2f  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdc34  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xdc39  castclass Microsoft.ReportingServices.Diagnostics.RunningJobContext
0xdc3e  stloc.2
0xdc3f  ldloc.2
0xdc40  brtrue.s loc_DC75
0xdc42  ldarg.0
0xdc43  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobsResolver::m_DbJobsToAdd
0xdc48  ldloc.1
0xdc49  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdc4e  ldloc.1
0xdc4f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xdc54  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xdc59  ldc.i4.4
0xdc5a  ldstr    aRunningjobsres// "RunningJobsResolver.Resolve: job: {0} w"...
0xdc5f  ldc.i4.1
0xdc60  newarr   [mscorlib]System.Object
0xdc65  dup
0xdc66  ldc.i4.0
0xdc67  ldloc.1
0xdc68  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdc6d  stelem.ref
0xdc6e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xdc73  br.s     loc_DCDE
0xdc75  ldloc.1
0xdc76  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Status()
0xdc7b  ldloc.2
0xdc7c  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Status()
0xdc81  beq.s    loc_DCBF
0xdc83  ldloc.2
0xdc84  callvirt instance valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Status()
0xdc89  ldc.i4.2
0xdc8a  bne.un.s loc_DCDE
0xdc8c  ldarg.0
0xdc8d  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobsResolver::m_MemJobsToCancel
0xdc92  ldloc.1
0xdc93  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdc98  ldloc.1
0xdc99  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xdc9e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xdca3  ldc.i4.4
0xdca4  ldstr    aRunningjobsres_0// "RunningJobsResolver.Resolve: job: {0} w"...
0xdca9  ldc.i4.1
0xdcaa  newarr   [mscorlib]System.Object
0xdcaf  dup
0xdcb0  ldc.i4.0
0xdcb1  ldloc.1
0xdcb2  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdcb7  stelem.ref
0xdcb8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xdcbd  br.s     loc_DCDE
0xdcbf  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xdcc4  ldc.i4.4
0xdcc5  ldstr    aRunningjobsres_1// "RunningJobsResolver.Resolve: job: {0} i"...
0xdcca  ldc.i4.1
0xdccb  newarr   [mscorlib]System.Object
0xdcd0  dup
0xdcd1  ldc.i4.0
0xdcd2  ldloc.1
0xdcd3  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdcd8  stelem.ref
0xdcd9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xdcde  ldloc.0
0xdcdf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xdce4  brtrue   loc_DC21
0xdce9  leave.s  loc_DCFC
0xdceb  ldloc.0
0xdcec  isinst   [mscorlib]System.IDisposable
0xdcf1  stloc.3
0xdcf2  ldloc.3
0xdcf3  brfalse.s loc_DCFB
0xdcf5  ldloc.3
0xdcf6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdcfb  endfinally
0xdcfc  ldarg.2
0xdcfd  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0xdd02  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xdd07  stloc.0
0xdd08  br.s     loc_DD5F
0xdd0a  ldloc.0
0xdd0b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xdd10  castclass Microsoft.ReportingServices.Diagnostics.RunningJobContext
0xdd15  stloc.s  4
0xdd17  ldarg.1
0xdd18  ldloc.s  4
0xdd1a  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdd1f  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xdd24  castclass Microsoft.ReportingServices.Diagnostics.RunningJobContext
0xdd29  brtrue.s loc_DD5F
0xdd2b  ldarg.0
0xdd2c  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningJobsResolver::m_DbJobsToRemove
0xdd31  ldloc.s  4
0xdd33  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdd38  ldloc.s  4
0xdd3a  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xdd3f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xdd44  ldc.i4.4
0xdd45  ldstr    aRunningjobsres_2// "RunningJobsResolver.Resolve: job: {0} w"...
0xdd4a  ldc.i4.1
0xdd4b  newarr   [mscorlib]System.Object
0xdd50  dup
0xdd51  ldc.i4.0
0xdd52  ldloc.s  4
0xdd54  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdd59  stelem.ref
0xdd5a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xdd5f  ldloc.0
0xdd60  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xdd65  brtrue.s loc_DD0A
0xdd67  leave.s  loc_DD7A
0xdd69  ldloc.0
0xdd6a  isinst   [mscorlib]System.IDisposable
0xdd6f  stloc.3
0xdd70  ldloc.3
0xdd71  brfalse.s loc_DD79
0xdd73  ldloc.3
0xdd74  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdd79  endfinally
0xdd7a  ret
```
