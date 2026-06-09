# Microsoft.ReportingServices.Diagnostics.RunningJobContext::.ctor

- ea: `0xd230`
- end: `0xd2d9`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobContext::.ctor`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xd970`

## callees

- `0x9260`
- `0x9310`
- `0xd400`
- `0xd770`

## pseudocode

```c

```

## disassembly

```asm
0xd230  ldarg.0
0xd231  ldc.i4.m1
0xd232  stfld    int32 Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_timeout
0xd237  ldarg.0
0xd238  newobj   instance void [mscorlib]System.Object::.ctor()
0xd23d  stfld    object Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_statusSyncRoot
0xd242  ldarg.0
0xd243  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xd248  call     class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.ArrayList::Synchronized(class [mscorlib]System.Collections.ArrayList)
0xd24d  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_threadsCtx
0xd252  ldarg.0
0xd253  call     instance void [mscorlib]System.Object::.ctor()
0xd258  ldnull
0xd259  newobj   instance void Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor(class Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator)
0xd25e  stloc.0
0xd25f  ldloc.0
0xd260  ldarg.2
0xd261  ldc.i4.8
0xd262  callvirt instance bool Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetPath(class Microsoft.ReportingServices.Diagnostics.ExternalItemPath externalPath, valuetype Microsoft.ReportingServices.Diagnostics.ItemPathOptions pathOptions)
0xd267  pop
0xd268  ldarg.0
0xd269  ldarg.1
0xd26a  stfld    string Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_jobId
0xd26f  ldarg.0
0xd270  ldloc.0
0xd271  callvirt instance var<u1> class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_OriginalItemPath()
0xd276  stfld    class Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_reqPath
0xd27b  ldarg.0
0xd27c  ldloc.0
0xd27d  callvirt instance string class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemName()
0xd282  stfld    string Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_reqName
0xd287  ldarg.0
0xd288  call     string [mscorlib]System.Environment::get_MachineName()
0xd28d  stfld    string Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_computerName
0xd292  ldarg.0
0xd293  ldarg.s  6
0xd295  stfld    class Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_userContext
0xd29a  ldarg.0
0xd29b  ldarg.s  5
0xd29d  stfld    class Microsoft.ReportingServices.Diagnostics.RunningJobList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_runningJobs
0xd2a2  ldarg.0
0xd2a3  ldarg.3
0xd2a4  stfld    valuetype Microsoft.ReportingServices.Diagnostics.JobActionEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_action
0xd2a9  ldarg.0
0xd2aa  ldarg.s  4
0xd2ac  stfld    class Microsoft.ReportingServices.Diagnostics.JobType Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_type
0xd2b1  ldarg.0
0xd2b2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xd2b7  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_startDate
0xd2bc  ldarg.0
0xd2bd  ldc.i4.0
0xd2be  stfld    valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_status
0xd2c3  ldarg.0
0xd2c4  ldarg.s  7
0xd2c6  stfld    class Microsoft.ReportingServices.Diagnostics.RequestContext Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_optionalContext
0xd2cb  ldarg.0
0xd2cc  call     instance void Microsoft.ReportingServices.Diagnostics.RunningJobContext::InitExecutionInfos()
0xd2d1  ldarg.0
0xd2d2  call     instance class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.RunningJobContext::AddWorkThread()
0xd2d7  pop
0xd2d8  ret
```
