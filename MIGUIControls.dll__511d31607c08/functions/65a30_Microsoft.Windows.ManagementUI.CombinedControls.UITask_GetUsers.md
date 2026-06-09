# Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetUsers

- ea: `0x65a30`
- end: `0x65b05`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetUsers`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x64880`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x5ee30`
- `0x5eee0`
- `0x645c0`
- `0x64680`
- `0x64710`
- `0x65a30`
- `0x67bb0`
- `0x67c50`
- `0x67e80`
- `0x85720`
- `0x85830`
- `0x85870`

## string_xrefs

- `0x65a8f`: `MessageTaskDoesNotExist`

## pseudocode

```c

```

## disassembly

```asm
0x65a30  ldarg.0
0x65a31  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x65a36  brfalse  loc_65B04
0x65a3b  ldarg.0
0x65a3c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x65a41  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IPrincipal Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition::get_Principal()
0x65a46  stloc.0
0x65a47  ldarg.0
0x65a48  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x65a4d  ldloc.0
0x65a4e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::LoadUserFromIPrinciple(class Microsoft.Windows.ManagementUI.CombinedControls.IPrincipal principal)
0x65a53  ldarg.0
0x65a54  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x65a59  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ITaskSettings Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition::get_Settings()
0x65a5e  callvirt instance valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskCompatibility Microsoft.Windows.ManagementUI.CombinedControls.ITaskSettings::get_Compatibility()
0x65a63  brtrue.s loc_65A7B
0x65a65  ldarg.0
0x65a66  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_User()
0x65a6b  ldarg.0
0x65a6c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x65a71  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x65a76  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskUser::LoadUserFromAtAccount(string computer)
0x65a7b  leave    loc_65B04
0x65a80  stloc.1
0x65a81  ldarg.0
0x65a82  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x65a87  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x65a8c  brtrue.s loc_65ABA
0x65a8e  ldnull
0x65a8f  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x65a94  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x65a99  ldc.i4.2
0x65a9a  newarr   [mscorlib]System.Object
0x65a9f  dup
0x65aa0  ldc.i4.0
0x65aa1  ldarg.0
0x65aa2  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x65aa7  stelem.ref
0x65aa8  dup
0x65aa9  ldc.i4.1
0x65aaa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x65aaf  stelem.ref
0x65ab0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x65ab5  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x65aba  ldloc.1
0x65abb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65ac0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x65ac5  leave.s  loc_65B04
0x65ac7  ldarg.0
0x65ac8  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x65acd  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x65ad2  brtrue.s loc_65AE3
0x65ad4  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x65ad9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x65ade  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x65ae3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65ae8  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x65aed  leave.s  loc_65B04
0x65aef  stloc.2
0x65af0  ldarg.0
0x65af1  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x65af6  ldloc.2
0x65af7  ldarg.0
0x65af8  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x65afd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x65b02  leave.s  loc_65B04
0x65b04  ret
```
