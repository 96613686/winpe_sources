# Microsoft.ReportingServices.Diagnostics.RunningJobContext::.ctor_0

- ea: `0xd2e0`
- end: `0xd3c9`
- name: `Microsoft.ReportingServices.Diagnostics.RunningJobContext::.ctor_0`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x4670`
- `0x8e20`
- `0x9e80`
- `0xd2e0`
- `0xd770`
- `0xeaa0`

## pseudocode

```c

```

## disassembly

```asm
0xd2e0  ldarg.0
0xd2e1  ldc.i4.m1
0xd2e2  stfld    int32 Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_timeout
0xd2e7  ldarg.0
0xd2e8  newobj   instance void [mscorlib]System.Object::.ctor()
0xd2ed  stfld    object Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_statusSyncRoot
0xd2f2  ldarg.0
0xd2f3  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xd2f8  call     class [mscorlib]System.Collections.ArrayList [mscorlib]System.Collections.ArrayList::Synchronized(class [mscorlib]System.Collections.ArrayList)
0xd2fd  stfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_threadsCtx
0xd302  ldarg.0
0xd303  call     instance void [mscorlib]System.Object::.ctor()
0xd308  ldarg.0
0xd309  ldarg.1
0xd30a  ldc.i4.0
0xd30b  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd310  stfld    string Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_jobId
0xd315  ldarg.0
0xd316  ldarg.1
0xd317  ldc.i4.1
0xd318  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0xd31d  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_startDate
0xd322  ldarg.0
0xd323  ldarg.1
0xd324  ldc.i4.2
0xd325  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd32a  stfld    string Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_computerName
0xd32f  ldarg.0
0xd330  ldarg.1
0xd331  ldc.i4.4
0xd332  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd337  newobj   instance void Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string value)
0xd33c  stfld    class Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_reqPath
0xd341  ldarg.0
0xd342  ldarg.1
0xd343  ldc.i4.3
0xd344  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd349  stfld    string Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_reqName
0xd34e  ldarg.1
0xd34f  ldc.i4.5
0xd350  ldc.i4.6
0xd351  call     string Microsoft.ReportingServices.Diagnostics.UserUtil::GetUserNameBySid(class [System.Data]System.Data.IDataRecord record, int32 indexNameBasedOnSid, int32 indexBackupUserName)
0xd356  stloc.0
0xd357  ldarg.1
0xd358  ldc.i4.s 0xC
0xd35a  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd35f  stloc.1
0xd360  ldarg.0
0xd361  ldloc.0
0xd362  ldnull
0xd363  ldloc.1
0xd364  newobj   instance void Microsoft.ReportingServices.Diagnostics.UserContext::.ctor(string userName, object token, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType authType)
0xd369  stfld    class Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_userContext
0xd36e  ldarg.1
0xd36f  ldc.i4.7
0xd370  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd375  brtrue.s loc_D384
0xd377  ldarg.0
0xd378  ldarg.1
0xd379  ldc.i4.7
0xd37a  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd37f  stfld    string Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_description
0xd384  ldarg.0
0xd385  ldarg.1
0xd386  ldc.i4.8
0xd387  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd38c  stfld    int32 Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_timeout
0xd391  ldarg.0
0xd392  ldarg.1
0xd393  ldc.i4.s 9
0xd395  callvirt instance int16 [System.Data]System.Data.IDataRecord::GetInt16(int32)
0xd39a  stfld    valuetype Microsoft.ReportingServices.Diagnostics.JobActionEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_action
0xd39f  ldarg.1
0xd3a0  ldc.i4.s 0xA
0xd3a2  callvirt instance int16 [System.Data]System.Data.IDataRecord::GetInt16(int32)
0xd3a7  stloc.2
0xd3a8  ldarg.0
0xd3a9  ldloc.2
0xd3aa  newobj   instance void Microsoft.ReportingServices.Diagnostics.JobType::.ctor(valuetype Microsoft.ReportingServices.Diagnostics.JobTypeEnum type)
0xd3af  stfld    class Microsoft.ReportingServices.Diagnostics.JobType Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_type
0xd3b4  ldarg.0
0xd3b5  ldarg.1
0xd3b6  ldc.i4.s 0xB
0xd3b8  callvirt instance int16 [System.Data]System.Data.IDataRecord::GetInt16(int32)
0xd3bd  stfld    valuetype Microsoft.ReportingServices.Diagnostics.JobStatusEnum Microsoft.ReportingServices.Diagnostics.RunningJobContext::m_status
0xd3c2  ldarg.0
0xd3c3  call     instance void Microsoft.ReportingServices.Diagnostics.RunningJobContext::InitExecutionInfos()
0xd3c8  ret
```
