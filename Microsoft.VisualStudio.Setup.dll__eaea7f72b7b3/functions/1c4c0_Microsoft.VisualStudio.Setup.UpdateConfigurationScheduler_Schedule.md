# Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::Schedule

- ea: `0x1c4c0`
- end: `0x1c5ab`
- name: `Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::Schedule`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5dc30`

## callees

- `0x1c4c0`
- `0x1c800`
- `0x1c8c0`
- `0x3f060`
- `0x49250`
- `0x49260`
- `0x49270`

## string_xrefs

- `0x1c526`: `Failed to map SID `
- `0x1c531`: ` when creating Update Configuration task`
- `0x1c56b`: `Failed to create the update configuration task for user `

## pseudocode

```c

```

## disassembly

```asm
0x1c4c0  ldarg.0
0x1c4c1  callvirt instance bool Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::ShouldRun()
0x1c4c6  brtrue.s loc_1C4C9
0x1c4c8  ret
0x1c4c9  ldarg.0
0x1c4ca  call     instance class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Principal.SecurityIdentifier> Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::GetUsers()
0x1c4cf  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Principal.SecurityIdentifier>::GetEnumerator()
0x1c4d4  stloc.0
0x1c4d5  br       loc_1C58E
0x1c4da  ldloca.s 0
0x1c4dc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Security.Principal.SecurityIdentifier>::get_Current()
0x1c4e1  stloc.1
0x1c4e2  ldarg.0
0x1c4e3  ldloc.1
0x1c4e4  call     instance class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::GetTaskDefinition(class [mscorlib]System.Security.Principal.SecurityIdentifier sid)
0x1c4e9  stloc.2
0x1c4ea  ldarg.0
0x1c4eb  call     instance class Microsoft.VisualStudio.Setup.Services.ITaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Scheduler()
0x1c4f0  ldloc.2
0x1c4f1  ldc.i4.0
0x1c4f2  callvirt instance void Microsoft.VisualStudio.Setup.Services.ITaskScheduler::Create(class Microsoft.VisualStudio.Setup.Services.IScheduledTaskDefinition definition, [opt] bool excludeUpdate)
0x1c4f7  leave    loc_1C58E
0x1c4fc  isinst   [System]System.ComponentModel.Win32Exception
0x1c501  dup
0x1c502  brtrue.s loc_1C508
0x1c504  pop
0x1c505  ldc.i4.0
0x1c506  br.s     loc_1C517
0x1c508  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x1c50d  ldc.i4   0x534
0x1c512  ceq
0x1c514  ldc.i4.0
0x1c515  cgt.un
0x1c517  endfilter
0x1c519  pop
0x1c51a  ldarg.0
0x1c51b  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x1c520  dup
0x1c521  brtrue.s loc_1C526
0x1c523  pop
0x1c524  br.s     loc_1C545
0x1c526  ldstr    aFailedToMapSid// "Failed to map SID "
0x1c52b  ldloc.1
0x1c52c  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x1c531  ldstr    aWhenCreatingUp// " when creating Update Configuration tas"...
0x1c536  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c53b  call     T0x2B000003
0x1c540  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1c545  leave.s  loc_1C58E
0x1c547  stloc.3
0x1c548  ldloc.1
0x1c549  ldtoken  [mscorlib]System.Security.Principal.NTAccount
0x1c54e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c553  callvirt instance class [mscorlib]System.Security.Principal.IdentityReference [mscorlib]System.Security.Principal.IdentityReference::Translate(class [mscorlib]System.Type)
0x1c558  callvirt instance string [mscorlib]System.Object::ToString()
0x1c55d  stloc.s  4
0x1c55f  ldarg.0
0x1c560  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x1c565  dup
0x1c566  brtrue.s loc_1C56B
0x1c568  pop
0x1c569  br.s     loc_1C58C
0x1c56b  ldstr    aFailedToCreate_0// "Failed to create the update configurati"...
0x1c570  ldloc.s  4
0x1c572  ldstr    asc_82BA2// ": "
0x1c577  ldloc.3
0x1c578  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1c57d  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1c582  call     T0x2B000003
0x1c587  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1c58c  leave.s  loc_1C58E
0x1c58e  ldloca.s 0
0x1c590  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Security.Principal.SecurityIdentifier>::MoveNext()
0x1c595  brtrue   loc_1C4DA
0x1c59a  leave.s  loc_1C5AA
0x1c59c  ldloca.s 0
0x1c59e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Security.Principal.SecurityIdentifier>
0x1c5a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c5a9  endfinally
0x1c5aa  ret
```
