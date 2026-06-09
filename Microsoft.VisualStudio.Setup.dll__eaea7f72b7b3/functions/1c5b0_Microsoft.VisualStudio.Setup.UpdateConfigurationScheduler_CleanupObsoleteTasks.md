# Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::CleanupObsoleteTasks

- ea: `0x1c5b0`
- end: `0x1c6d3`
- name: `Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::CleanupObsoleteTasks`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x60500`

## callees

- `0x1c5b0`
- `0x1c6e0`
- `0x1c800`
- `0x3edb0`
- `0x3ee20`
- `0x3f070`
- `0x3f0c0`
- `0x49250`
- `0x49260`

## string_xrefs

- `0x1c62e`: `Update Configuration Obsolete Task Cleanup - Can't resolve SID for account `
- `0x1c678`: `Removing obsolete update configuration task `

## pseudocode

```c

```

## disassembly

```asm
0x1c5b0  ldarg.0
0x1c5b1  call     instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Principal.SecurityIdentifier> Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::GetUsers()
0x1c5b6  stloc.0
0x1c5b7  ldarg.0
0x1c5b8  call     instance class Microsoft.VisualStudio.Setup.Services.ITaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Scheduler()
0x1c5bd  ldsfld   string Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::UpdataConfigurationTaskPath
0x1c5c2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails> Microsoft.VisualStudio.Setup.Services.ITaskScheduler::GetTaskDetailsForFolder(string folderPath)
0x1c5c7  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails, bool> <>c::<>9__7_0
0x1c5cc  dup
0x1c5cd  brtrue.s loc_1C5E6
0x1c5cf  pop
0x1c5d0  ldsfld   class <>c <>c::<>9
0x1c5d5  ldftn    instance bool <>c::<CleanupObsoleteTasks>b__7_0(class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails x)
0x1c5db  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails, bool>::.ctor(object, native int)
0x1c5e0  dup
0x1c5e1  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails, bool> <>c::<>9__7_0
0x1c5e6  call     T0x2B00010B
0x1c5eb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails>::GetEnumerator()
0x1c5f0  stloc.1
0x1c5f1  br       loc_1C6BB
0x1c5f6  ldloc.1
0x1c5f7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails>::get_Current()
0x1c5fc  stloc.2
0x1c5fd  ldnull
0x1c5fe  stloc.3
0x1c5ff  ldloc.2
0x1c600  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails::get_UserAccount()
0x1c605  newobj   instance void [mscorlib]System.Security.Principal.NTAccount::.ctor(string)
0x1c60a  ldtoken  [mscorlib]System.Security.Principal.SecurityIdentifier
0x1c60f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c614  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x1c619  castclass [mscorlib]System.Security.Principal.SecurityIdentifier
0x1c61e  stloc.3
0x1c61f  leave.s  loc_1C64F
0x1c621  pop
0x1c622  ldarg.0
0x1c623  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x1c628  dup
0x1c629  brtrue.s loc_1C62E
0x1c62b  pop
0x1c62c  br.s     loc_1C64D
0x1c62e  ldstr    aUpdateConfigur// "Update Configuration Obsolete Task Clea"...
0x1c633  ldloc.2
0x1c634  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails::get_UserAccount()
0x1c639  ldstr    asc_80DBA// "."
0x1c63e  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c643  call     T0x2B000003
0x1c648  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1c64d  leave.s  loc_1C64F
0x1c64f  ldloc.3
0x1c650  brfalse.s loc_1C664
0x1c652  ldloc.0
0x1c653  ldloc.3
0x1c654  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Principal.SecurityIdentifier>::Contains(var<u1>)
0x1c659  brfalse.s loc_1C664
0x1c65b  ldarg.0
0x1c65c  ldloc.3
0x1c65d  call     instance bool Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::IsValidSidForUpdateConfiguration(class [mscorlib]System.Security.Principal.SecurityIdentifier sid)
0x1c662  brtrue.s loc_1C6BB
0x1c664  ldarg.0
0x1c665  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x1c66a  dup
0x1c66b  brtrue.s loc_1C670
0x1c66d  pop
0x1c66e  br.s     loc_1C6AF
0x1c670  ldc.i4.5
0x1c671  newarr   [mscorlib]System.String
0x1c676  dup
0x1c677  ldc.i4.0
0x1c678  ldstr    aRemovingObsole// "Removing obsolete update configuration "...
0x1c67d  stelem.ref
0x1c67e  dup
0x1c67f  ldc.i4.1
0x1c680  ldloc.2
0x1c681  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition::get_Name()
0x1c686  stelem.ref
0x1c687  dup
0x1c688  ldc.i4.2
0x1c689  ldstr    aForAccount// " for account "
0x1c68e  stelem.ref
0x1c68f  dup
0x1c690  ldc.i4.3
0x1c691  ldloc.2
0x1c692  callvirt instance string Microsoft.VisualStudio.Setup.Services.IScheduledTaskDetails::get_UserAccount()
0x1c697  stelem.ref
0x1c698  dup
0x1c699  ldc.i4.4
0x1c69a  ldstr    asc_80DBA// "."
0x1c69f  stelem.ref
0x1c6a0  call     string [mscorlib]System.String::Concat(string[])
0x1c6a5  call     T0x2B000003
0x1c6aa  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1c6af  ldarg.0
0x1c6b0  call     instance class Microsoft.VisualStudio.Setup.Services.ITaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Scheduler()
0x1c6b5  ldloc.2
0x1c6b6  callvirt instance void Microsoft.VisualStudio.Setup.Services.ITaskScheduler::Remove(class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition definition)
0x1c6bb  ldloc.1
0x1c6bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c6c1  brtrue   loc_1C5F6
0x1c6c6  leave.s  loc_1C6D2
0x1c6c8  ldloc.1
0x1c6c9  brfalse.s loc_1C6D1
0x1c6cb  ldloc.1
0x1c6cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c6d1  endfinally
0x1c6d2  ret
```
