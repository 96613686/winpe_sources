# Microsoft.Windows.ManagementUI.CombinedControls.UITask::LoadFromTaskDefinition_0

- ea: `0x64880`
- end: `0x64a1f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::LoadFromTaskDefinition_0`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x64870`
- `0x6bd20`

## callees

- `0x12ed0`
- `0x13430`
- `0x13440`
- `0x5d760`
- `0x5de60`
- `0x63130`
- `0x63840`
- `0x645c0`
- `0x645d0`
- `0x646a0`
- `0x646c0`
- `0x64880`
- `0x65890`
- `0x65a30`
- `0x65b10`
- `0x65cd0`
- `0x67c50`
- `0x67e80`
- `0x83bf0`

## string_xrefs

- `0x64931`: `ApplicationTaskScheduler`
- `0x649b6`: `ApplicationTaskScheduler`
- `0x649eb`: `ApplicationTaskScheduler`
- `0x64990`: `MessageTaskDoesNotExist`
- `0x64913`: `MessageInvalidTaskFormat`

## pseudocode

```c

```

## disassembly

```asm
0x64880  ldc.i4.0
0x64881  stloc.0
0x64882  ldarg.0
0x64883  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x64888  brfalse.s loc_6489B
0x6488a  ldarg.0
0x6488b  ldarg.0
0x6488c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x64891  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask::get_Definition()
0x64896  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x6489b  ldarg.0
0x6489c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x648a1  brfalse.s loc_648E9
0x648a3  ldarg.0
0x648a4  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x648a9  stloc.1
0x648aa  ldarg.0
0x648ab  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetTaskPreviewAndRegistrationInformation()
0x648b0  brfalse.s loc_648E9
0x648b2  ldarg.0
0x648b3  ldloc.1
0x648b4  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITask::set_Name(string value)
0x648b9  ldarg.0
0x648ba  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetActions()
0x648bf  ldarg.0
0x648c0  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UIConditions Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Conditions()
0x648c5  ldarg.0
0x648c6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x648cb  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIConditions::LoadConditionsFromJob(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition newJob)
0x648d0  ldarg.0
0x648d1  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_AdvancedSettings()
0x648d6  ldarg.0
0x648d7  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x648dc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskAdvancedSettings::LoadSettingsFromJob(class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition newJob)
0x648e1  ldarg.0
0x648e2  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetUsers()
0x648e7  ldc.i4.1
0x648e8  stloc.0
0x648e9  ldarg.0
0x648ea  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITask::OverrideInvalidDefaults()
0x648ef  leave    loc_64A1D
0x648f4  stloc.2
0x648f5  ldloc.2
0x648f6  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x648fb  stloc.3
0x648fc  ldloc.3
0x648fd  ldc.i4   0xC00CEE04
0x64902  bne.un.s loc_64942
0x64904  ldarg.0
0x64905  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x6490a  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x6490f  brtrue.s loc_6497A
0x64911  ldarg.1
0x64912  ldnull
0x64913  ldstr    aMessageinvalid_3// "MessageInvalidTaskFormat"
0x64918  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6491d  ldc.i4.1
0x6491e  newarr   [mscorlib]System.Object
0x64923  dup
0x64924  ldc.i4.0
0x64925  ldarg.0
0x64926  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x6492b  stelem.ref
0x6492c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x64931  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x64936  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6493b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x64940  br.s     loc_6497A
0x64942  ldloc.3
0x64943  ldc.i4   0x8000FFFF
0x64948  bne.un.s loc_64957
0x6494a  ldloc.2
0x6494b  callvirt instance string [mscorlib]System.Object::ToString()
0x64950  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64955  br.s     loc_6497A
0x64957  ldloc.3
0x64958  ldc.i4   0x80070241
0x6495d  bne.un.s loc_6496C
0x6495f  ldloc.2
0x64960  callvirt instance string [mscorlib]System.Object::ToString()
0x64965  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x6496a  br.s     loc_6497A
0x6496c  ldarg.0
0x6496d  ldloc.2
0x6496e  ldarg.0
0x6496f  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64974  ldc.i4.1
0x64975  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ProcessExternalErrors(class [mscorlib]System.Runtime.InteropServices.ExternalException e, string taskName, bool showToUser)
0x6497a  leave    loc_64A1D
0x6497f  stloc.s  4
0x64981  ldarg.0
0x64982  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64987  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x6498c  brtrue.s loc_649C5
0x6498e  ldarg.1
0x6498f  ldnull
0x64990  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x64995  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6499a  ldc.i4.2
0x6499b  newarr   [mscorlib]System.Object
0x649a0  dup
0x649a1  ldc.i4.0
0x649a2  ldarg.0
0x649a3  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x649a8  stelem.ref
0x649a9  dup
0x649aa  ldc.i4.1
0x649ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x649b0  stelem.ref
0x649b1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x649b6  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x649bb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x649c0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x649c5  ldloc.s  4
0x649c7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x649cc  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x649d1  leave.s  loc_64A1D
0x649d3  ldarg.0
0x649d4  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x649d9  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x649de  brtrue.s loc_649FA
0x649e0  ldarg.1
0x649e1  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x649e6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x649eb  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x649f0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x649f5  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x649fa  callvirt instance string [mscorlib]System.Exception::get_Message()
0x649ff  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64a04  leave.s  loc_64A1D
0x64a06  stloc.s  5
0x64a08  ldarg.0
0x64a09  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64a0e  ldloc.s  5
0x64a10  ldarg.0
0x64a11  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64a16  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x64a1b  leave.s  loc_64A1D
0x64a1d  ldloc.0
0x64a1e  ret
```
