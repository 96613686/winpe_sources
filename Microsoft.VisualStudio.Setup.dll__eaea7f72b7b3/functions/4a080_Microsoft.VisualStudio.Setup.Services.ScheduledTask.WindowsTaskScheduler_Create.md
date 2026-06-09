# Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::Create

- ea: `0x4a080`
- end: `0x4a2c2`
- name: `Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::Create`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x49110`
- `0x49480`
- `0x494a0`
- `0x494c0`
- `0x494e0`
- `0x49500`
- `0x49520`
- `0x49560`
- `0x49570`
- `0x49ce0`
- `0x49d00`
- `0x49d20`
- `0x49d60`
- `0x49d80`
- `0x49da0`
- `0x4a080`
- `0x4a9b0`
- `0x4ab50`
- `0x4abb0`
- `0x4ae50`
- `0x4aeb0`
- `0x62750`
- `0x62770`
- `0x627a0`
- `0x62850`
- `0x62870`
- `0x628a0`
- `0x628f0`
- `0x62960`
- `0x62a50`
- `0x62ac0`
- `0x62ad0`

## string_xrefs

- `0x4a2a5`: `Failed to create scheduled task: `
- `0x4a09c`: `Expects TaskDefinition to be passed in`

## pseudocode

```c

```

## disassembly

```asm
0x4a080  ldarg.1
0x4a081  ldstr    aDefinition// "definition"
0x4a086  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x4a08b  ldarg.0
0x4a08c  call     instance class WindowsTaskSchedulerInterop.TaskScheduler Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::GetTaskScheduler()
0x4a091  stloc.0
0x4a092  ldarg.1
0x4a093  isinst   Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition
0x4a098  stloc.1
0x4a099  ldloc.1
0x4a09a  brtrue.s loc_4A0A7
0x4a09c  ldstr    aExpectsTaskdef// "Expects TaskDefinition to be passed in"
0x4a0a1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4a0a6  throw
0x4a0a7  nop
0x4a0a8  ldloc.0
0x4a0a9  ldsfld   object [mscorlib]System.Type::Missing
0x4a0ae  ldsfld   object [mscorlib]System.Type::Missing
0x4a0b3  ldsfld   object [mscorlib]System.Type::Missing
0x4a0b8  ldsfld   object [mscorlib]System.Type::Missing
0x4a0bd  callvirt instance void WindowsTaskSchedulerInterop.ITaskService::Connect([in] [opt] [hasfieldmarshal] object serverName, [in] [opt] [hasfieldmarshal] object user, [in] [opt] [hasfieldmarshal] object domain, [in] [opt] [hasfieldmarshal] object password)
0x4a0c2  ldloc.0
0x4a0c3  ldc.i4.0
0x4a0c4  callvirt instance class WindowsTaskSchedulerInterop.ITaskDefinition WindowsTaskSchedulerInterop.ITaskService::NewTask([hasfieldmarshal] unsigned int32)
0x4a0c9  stloc.2
0x4a0ca  ldloc.2
0x4a0cb  callvirt instance class WindowsTaskSchedulerInterop.IRegistrationInfo WindowsTaskSchedulerInterop.ITaskDefinition::get_RegistrationInfo()
0x4a0d0  ldloc.1
0x4a0d1  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRegistrationInfo Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_RegistrationInfo()
0x4a0d6  dup
0x4a0d7  brtrue.s loc_4A0DD
0x4a0d9  pop
0x4a0da  ldnull
0x4a0db  br.s     loc_4A0E2
0x4a0dd  call     instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRegistrationInfo::get_Author()
0x4a0e2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a0e7  brfalse.s loc_4A0F0
0x4a0e9  ldsfld   string Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::Author
0x4a0ee  br.s     loc_4A0FB
0x4a0f0  ldloc.1
0x4a0f1  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRegistrationInfo Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_RegistrationInfo()
0x4a0f6  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRegistrationInfo::get_Author()
0x4a0fb  callvirt instance void WindowsTaskSchedulerInterop.IRegistrationInfo::set_Author([in] [hasfieldmarshal] string pAuthor)
0x4a100  ldloc.2
0x4a101  callvirt instance class WindowsTaskSchedulerInterop.IRegistrationInfo WindowsTaskSchedulerInterop.ITaskDefinition::get_RegistrationInfo()
0x4a106  ldloc.1
0x4a107  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRegistrationInfo Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_RegistrationInfo()
0x4a10c  dup
0x4a10d  brtrue.s loc_4A113
0x4a10f  pop
0x4a110  ldnull
0x4a111  br.s     loc_4A118
0x4a113  call     instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRegistrationInfo::get_Date()
0x4a118  callvirt instance void WindowsTaskSchedulerInterop.IRegistrationInfo::set_Date([in] [hasfieldmarshal] string pDate)
0x4a11d  ldloc.2
0x4a11e  callvirt instance class WindowsTaskSchedulerInterop.IRegistrationInfo WindowsTaskSchedulerInterop.ITaskDefinition::get_RegistrationInfo()
0x4a123  ldloc.1
0x4a124  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRegistrationInfo Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_RegistrationInfo()
0x4a129  dup
0x4a12a  brtrue.s loc_4A130
0x4a12c  pop
0x4a12d  ldnull
0x4a12e  br.s     loc_4A135
0x4a130  call     instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRegistrationInfo::get_Description()
0x4a135  callvirt instance void WindowsTaskSchedulerInterop.IRegistrationInfo::set_Description([in] [hasfieldmarshal] string pDescription)
0x4a13a  ldarg.0
0x4a13b  ldloc.1
0x4a13c  ldloc.2
0x4a13d  call     instance void Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::SetSettings(class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition inputDefinition, class WindowsTaskSchedulerInterop.ITaskDefinition taskDefinition)
0x4a142  ldloc.2
0x4a143  callvirt instance class WindowsTaskSchedulerInterop.IPrincipal WindowsTaskSchedulerInterop.ITaskDefinition::get_Principal()
0x4a148  ldloc.1
0x4a149  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Principal()
0x4a14e  brtrue.s loc_4A15C
0x4a150  ldsfld   unsigned int8[] Microsoft.VisualStudio.Setup.Services.ScheduledTask.ScheduledTaskUtilities::SystemSid
0x4a155  callvirt instance string [mscorlib]System.Object::ToString()
0x4a15a  br.s     loc_4A175
0x4a15c  ldloc.1
0x4a15d  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Principal()
0x4a162  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal::get_UserId()
0x4a167  dup
0x4a168  brtrue.s loc_4A175
0x4a16a  pop
0x4a16b  ldsfld   unsigned int8[] Microsoft.VisualStudio.Setup.Services.ScheduledTask.ScheduledTaskUtilities::SystemSid
0x4a170  callvirt instance string [mscorlib]System.Object::ToString()
0x4a175  callvirt instance void WindowsTaskSchedulerInterop.IPrincipal::set_UserId([in] [hasfieldmarshal] string pUser)
0x4a17a  ldloc.2
0x4a17b  callvirt instance class WindowsTaskSchedulerInterop.IPrincipal WindowsTaskSchedulerInterop.ITaskDefinition::get_Principal()
0x4a180  ldloc.1
0x4a181  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Principal()
0x4a186  brtrue.s loc_4A18B
0x4a188  ldc.i4.0
0x4a189  br.s     loc_4A196
0x4a18b  ldloc.1
0x4a18c  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Principal()
0x4a191  callvirt instance valuetype Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskLogonType Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal::get_LogonType()
0x4a196  callvirt instance void WindowsTaskSchedulerInterop.IPrincipal::set_LogonType([in] valuetype WindowsTaskSchedulerInterop._TASK_LOGON_TYPE pLogon)
0x4a19b  ldloc.2
0x4a19c  callvirt instance class WindowsTaskSchedulerInterop.IPrincipal WindowsTaskSchedulerInterop.ITaskDefinition::get_Principal()
0x4a1a1  ldloc.1
0x4a1a2  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Principal()
0x4a1a7  brtrue.s loc_4A1AC
0x4a1a9  ldc.i4.0
0x4a1aa  br.s     loc_4A1B7
0x4a1ac  ldloc.1
0x4a1ad  callvirt instance class Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Principal()
0x4a1b2  callvirt instance valuetype Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskRunLevel Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskPrincipal::get_RunLevel()
0x4a1b7  callvirt instance void WindowsTaskSchedulerInterop.IPrincipal::set_RunLevel([in] valuetype WindowsTaskSchedulerInterop._TASK_RUNLEVEL pRunLevel)
0x4a1bc  ldloc.1
0x4a1bd  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Services.ScheduledTask.ITaskAction> Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Actions()
0x4a1c2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Services.ScheduledTask.ITaskAction>::GetEnumerator()
0x4a1c7  stloc.s  6
0x4a1c9  br.s     loc_4A1DD
0x4a1cb  ldloc.s  6
0x4a1cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Services.ScheduledTask.ITaskAction>::get_Current()
0x4a1d2  stloc.s  7
0x4a1d4  ldarg.0
0x4a1d5  ldloc.s  7
0x4a1d7  ldloc.2
0x4a1d8  call     instance void Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::SetAction(class Microsoft.VisualStudio.Setup.Services.ScheduledTask.ITaskAction action, class WindowsTaskSchedulerInterop.ITaskDefinition taskDefinition)
0x4a1dd  ldloc.s  6
0x4a1df  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a1e4  brtrue.s loc_4A1CB
0x4a1e6  leave.s  loc_4A1F4
0x4a1e8  ldloc.s  6
0x4a1ea  brfalse.s loc_4A1F3
0x4a1ec  ldloc.s  6
0x4a1ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a1f3  endfinally
0x4a1f4  ldloc.1
0x4a1f5  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Services.ScheduledTask.ITaskTrigger> Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Triggers()
0x4a1fa  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Services.ScheduledTask.ITaskTrigger>::GetEnumerator()
0x4a1ff  stloc.s  8
0x4a201  br.s     loc_4A215
0x4a203  ldloc.s  8
0x4a205  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Services.ScheduledTask.ITaskTrigger>::get_Current()
0x4a20a  stloc.s  9
0x4a20c  ldarg.0
0x4a20d  ldloc.s  9
0x4a20f  ldloc.2
0x4a210  call     instance void Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::SetTrigger(class Microsoft.VisualStudio.Setup.Services.ScheduledTask.ITaskTrigger trigger, class WindowsTaskSchedulerInterop.ITaskDefinition taskDefinition)
0x4a215  ldloc.s  8
0x4a217  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a21c  brtrue.s loc_4A203
0x4a21e  leave.s  loc_4A22C
0x4a220  ldloc.s  8
0x4a222  brfalse.s loc_4A22B
0x4a224  ldloc.s  8
0x4a226  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a22b  endfinally
0x4a22c  ldloc.1
0x4a22d  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Directory()
0x4a232  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a237  brfalse.s loc_4A240
0x4a239  ldsfld   string Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::VisualStudioScheduledTaskPath
0x4a23e  br.s     loc_4A246
0x4a240  ldloc.1
0x4a241  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Directory()
0x4a246  stloc.3
0x4a247  ldarg.0
0x4a248  ldloc.0
0x4a249  ldloc.3
0x4a24a  ldc.i4.1
0x4a24b  call     instance class WindowsTaskSchedulerInterop.ITaskFolder Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::GetFolder(class WindowsTaskSchedulerInterop.TaskScheduler taskScheduler, string directory, [opt] bool createIfNotExist)
0x4a250  ldarg.2
0x4a251  brtrue.s loc_4A256
0x4a253  ldc.i4.6
0x4a254  br.s     loc_4A257
0x4a256  ldc.i4.2
0x4a257  stloc.s  4
0x4a259  ldloc.1
0x4a25a  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_UserAccount()
0x4a25f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a264  brfalse.s loc_4A272
0x4a266  ldsfld   unsigned int8[] Microsoft.VisualStudio.Setup.Services.ScheduledTask.ScheduledTaskUtilities::SystemSid
0x4a26b  call     string Microsoft.VisualStudio.Setup.Services.ScheduledTask.ScheduledTaskUtilities::GetAccountName(unsigned int8[] sid)
0x4a270  br.s     loc_4A278
0x4a272  ldloc.1
0x4a273  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_UserAccount()
0x4a278  stloc.s  5
0x4a27a  ldloc.1
0x4a27b  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Name()
0x4a280  ldloc.2
0x4a281  ldloc.s  4
0x4a283  ldloc.s  5
0x4a285  ldnull
0x4a286  ldloc.1
0x4a287  callvirt instance valuetype Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskLogonType Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_LogonType()
0x4a28c  ldnull
0x4a28d  callvirt instance class WindowsTaskSchedulerInterop.IRegisteredTask WindowsTaskSchedulerInterop.ITaskFolder::RegisterTaskDefinition([hasfieldmarshal] string, [in] [hasfieldmarshal] class WindowsTaskSchedulerInterop.ITaskDefinition Path, [in] [hasfieldmarshal] int32 pDefinition, [in] object flags, [in] [hasfieldmarshal] object UserId, [in] [hasfieldmarshal] valuetype WindowsTaskSchedulerInterop._TASK_LOGON_TYPE password, [in] object LogonType)
0x4a292  pop
0x4a293  leave.s  loc_4A2C1
0x4a295  stloc.s  0xA
0x4a297  ldarg.0
0x4a298  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.WindowsTaskScheduler::logger
0x4a29d  dup
0x4a29e  brtrue.s loc_4A2A3
0x4a2a0  pop
0x4a2a1  br.s     loc_4A2BF
0x4a2a3  ldloc.s  0xA
0x4a2a5  ldstr    aFailedToCreate_11// "Failed to create scheduled task: "
0x4a2aa  ldloc.1
0x4a2ab  callvirt instance string Microsoft.VisualStudio.Setup.Services.ScheduledTask.TaskDefinition::get_Name()
0x4a2b0  call     string [mscorlib]System.String::Concat(string, string)
0x4a2b5  call     T0x2B000003
0x4a2ba  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x4a2bf  rethrow
0x4a2c1  ret
```
