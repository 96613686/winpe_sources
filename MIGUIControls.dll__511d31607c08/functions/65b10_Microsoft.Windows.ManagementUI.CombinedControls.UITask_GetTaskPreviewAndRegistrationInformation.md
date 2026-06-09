# Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetTaskPreviewAndRegistrationInformation

- ea: `0x65b10`
- end: `0x65c68`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetTaskPreviewAndRegistrationInformation`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x64880`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x640d0`
- `0x642d0`
- `0x642f0`
- `0x64310`
- `0x64330`
- `0x64350`
- `0x64390`
- `0x64490`
- `0x645c0`
- `0x64620`
- `0x64630`
- `0x64720`
- `0x65b10`
- `0x660d0`
- `0x67c50`
- `0x67e80`

## string_xrefs

- `0x65bf1`: `MessageTaskDoesNotExist`

## pseudocode

```c

```

## disassembly

```asm
0x65b10  ldc.i4.0
0x65b11  stloc.0
0x65b12  ldarg.0
0x65b13  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.UITask::stringTaskName
0x65b18  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x65b1d  brtrue.s loc_65B25
0x65b1f  ldarg.0
0x65b20  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITask::Reset()
0x65b25  ldarg.0
0x65b26  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x65b2b  ldsfld   string [mscorlib]System.String::Empty
0x65b30  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::set_LastRunResult(string value)
0x65b35  ldarg.0
0x65b36  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x65b3b  ldsfld   string [mscorlib]System.String::Empty
0x65b40  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::set_NextRunTime(string value)
0x65b45  ldarg.0
0x65b46  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x65b4b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x65b50  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::set_NextRunDateTime(valuetype [mscorlib]System.DateTime value)
0x65b55  ldarg.0
0x65b56  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x65b5b  ldsfld   string [mscorlib]System.String::Empty
0x65b60  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::set_LastRunTime(string value)
0x65b65  ldarg.0
0x65b66  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x65b6b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x65b70  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::set_LastRunTimeInDateTimeType(valuetype [mscorlib]System.DateTime value)
0x65b75  ldarg.0
0x65b76  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_RegistrationInfo()
0x65b7b  ldarg.0
0x65b7c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x65b81  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskRegistrationInfo::LoadRegistrationInfoFromJob(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition newJob)
0x65b86  ldarg.0
0x65b87  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x65b8c  ldarg.0
0x65b8d  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetTriggers()
0x65b92  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::set_TriggerDescription(string value)
0x65b97  ldarg.0
0x65b98  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_PreviewInfo()
0x65b9d  ldarg.0
0x65b9e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x65ba3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskPreviewGeneratedInfo::LoadPreviewInfoFromJob(class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask registeredTask)
0x65ba8  ldc.i4.1
0x65ba9  stloc.0
0x65baa  leave    loc_65C66
0x65baf  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65bb4  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x65bb9  leave    loc_65C66
0x65bbe  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65bc3  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x65bc8  leave    loc_65C66
0x65bcd  pop
0x65bce  leave    loc_65C66
0x65bd3  callvirt instance string [mscorlib]System.Object::ToString()
0x65bd8  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x65bdd  leave    loc_65C66
0x65be2  stloc.1
0x65be3  ldarg.0
0x65be4  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x65be9  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x65bee  brtrue.s loc_65C1C
0x65bf0  ldnull
0x65bf1  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x65bf6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x65bfb  ldc.i4.2
0x65bfc  newarr   [mscorlib]System.Object
0x65c01  dup
0x65c02  ldc.i4.0
0x65c03  ldarg.0
0x65c04  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x65c09  stelem.ref
0x65c0a  dup
0x65c0b  ldc.i4.1
0x65c0c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x65c11  stelem.ref
0x65c12  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x65c17  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x65c1c  ldloc.1
0x65c1d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65c22  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x65c27  leave.s  loc_65C66
0x65c29  ldarg.0
0x65c2a  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x65c2f  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x65c34  brtrue.s loc_65C45
0x65c36  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x65c3b  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x65c40  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x65c45  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65c4a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x65c4f  leave.s  loc_65C66
0x65c51  stloc.2
0x65c52  ldarg.0
0x65c53  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x65c58  ldloc.2
0x65c59  ldarg.0
0x65c5a  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x65c5f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x65c64  leave.s  loc_65C66
0x65c66  ldloc.0
0x65c67  ret
```
