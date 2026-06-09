# Microsoft.ReportingServices.Diagnostics.RunningJobList::InternalCancel

- ea: `0xdad0`
- end: `0xdb24`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobList::InternalCancel`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xda50`

## callees

- `0xd510`
- `0xd600`
- `0xd6b0`
- `0xdad0`
- `0x10310`

## pseudocode

```c

```

## disassembly

```asm
0xdad0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xdad5  ldc.i4.3
0xdad6  ldstr    aRunningjoblist_2// "RunningJobList.CancelJob; found job: "
0xdadb  ldarg.1
0xdadc  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0xdae1  ldstr    aLocallyCancell// "locally; Cancelling..."
0xdae6  call     string [mscorlib]System.String::Concat(string, string, string)
0xdaeb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xdaf0  ldarg.1
0xdaf1  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Machine()
0xdaf6  call     string [mscorlib]System.Environment::get_MachineName()
0xdafb  ldc.i4.4
0xdafc  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xdb01  brfalse.s loc_DB19
0xdb03  ldstr    aFoundUnexpecte// "Found unexpected job for machine: "
0xdb08  ldarg.1
0xdb09  callvirt instance string Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Machine()
0xdb0e  call     string [mscorlib]System.String::Concat(string, string)
0xdb13  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0xdb18  throw
0xdb19  ldarg.1
0xdb1a  ldarg.2
0xdb1b  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.RunningJobContext::Cancel(valuetype AbortReason reason)
0xdb20  ldc.i4.0
0xdb21  cgt
0xdb23  ret
```
