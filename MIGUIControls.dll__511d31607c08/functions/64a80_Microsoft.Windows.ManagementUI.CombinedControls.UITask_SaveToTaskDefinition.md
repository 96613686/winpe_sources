# Microsoft.Windows.ManagementUI.CombinedControls.UITask::SaveToTaskDefinition

- ea: `0x64a80`
- end: `0x64b9b`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::SaveToTaskDefinition`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x65050`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x5ef60`
- `0x63060`
- `0x63710`
- `0x63ea0`
- `0x645c0`
- `0x64630`
- `0x64680`
- `0x646a0`
- `0x646c0`
- `0x64a80`
- `0x64ba0`
- `0x65e90`
- `0x66580`
- `0x67c50`
- `0x67e80`
- `0x83c00`
- `0x858c0`

## string_xrefs

- `0x64b24`: `MessageTaskDoesNotExist`

## pseudocode

```c

```

## disassembly

```asm
0x64a80  ldc.i4.0
0x64a81  stloc.0
0x64a82  ldarg.0
0x64a83  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x64a88  brfalse.s loc_64AA0
0x64a8a  ldarg.0
0x64a8b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64a90  ldarg.0
0x64a91  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x64a96  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask::get_XML()
0x64a9b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition::set_XmlText(string value)
0x64aa0  ldarg.0
0x64aa1  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::ResetExistingTaskDefinition()
0x64aa6  pop
0x64aa7  ldarg.0
0x64aa8  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x64aad  ldarg.0
0x64aae  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64ab3  ldarg.1
0x64ab4  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::PutRegistrationInfoIntoJob(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition& job, bool isNewTask)
0x64ab9  brfalse.s loc_64B10
0x64abb  ldarg.0
0x64abc  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x64ac1  ldarg.0
0x64ac2  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64ac7  ldarg.1
0x64ac8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::PutUserIntoITaskDefinition(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition& taskDefinition, bool isNewTask)
0x64acd  ldarg.0
0x64ace  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Conditions()
0x64ad3  ldarg.0
0x64ad4  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64ad9  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::PutConditionsIntoJob(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition& newJob)
0x64ade  brfalse.s loc_64B10
0x64ae0  ldarg.0
0x64ae1  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_AdvancedSettings()
0x64ae6  ldarg.0
0x64ae7  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64aec  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::PutSettingsIntoJob(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition& newJob)
0x64af1  brfalse.s loc_64B10
0x64af3  ldarg.0
0x64af4  ldarg.0
0x64af5  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64afa  ldarg.1
0x64afb  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::SetTriggers(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition& newJob, bool addNewFlag)
0x64b00  brfalse.s loc_64B10
0x64b02  ldarg.0
0x64b03  ldarg.0
0x64b04  ldflda   class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64b09  ldarg.1
0x64b0a  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::SetActions(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition& newJob, bool addNewFlag)
0x64b0f  stloc.0
0x64b10  leave    loc_64B99
0x64b15  stloc.1
0x64b16  ldarg.0
0x64b17  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64b1c  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x64b21  brtrue.s loc_64B4F
0x64b23  ldnull
0x64b24  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x64b29  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64b2e  ldc.i4.2
0x64b2f  newarr   [mscorlib]System.Object
0x64b34  dup
0x64b35  ldc.i4.0
0x64b36  ldarg.0
0x64b37  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64b3c  stelem.ref
0x64b3d  dup
0x64b3e  ldc.i4.1
0x64b3f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x64b44  stelem.ref
0x64b45  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x64b4a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x64b4f  ldloc.1
0x64b50  callvirt instance string [mscorlib]System.Exception::get_Message()
0x64b55  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64b5a  leave.s  loc_64B99
0x64b5c  ldarg.0
0x64b5d  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64b62  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x64b67  brtrue.s loc_64B78
0x64b69  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x64b6e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64b73  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x64b78  callvirt instance string [mscorlib]System.Exception::get_Message()
0x64b7d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64b82  leave.s  loc_64B99
0x64b84  stloc.2
0x64b85  ldarg.0
0x64b86  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64b8b  ldloc.2
0x64b8c  ldarg.0
0x64b8d  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64b92  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x64b97  leave.s  loc_64B99
0x64b99  ldloc.0
0x64b9a  ret
```
