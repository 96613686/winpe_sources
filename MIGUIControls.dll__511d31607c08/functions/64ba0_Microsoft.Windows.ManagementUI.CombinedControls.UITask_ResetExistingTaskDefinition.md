# Microsoft.Windows.ManagementUI.CombinedControls.UITask::ResetExistingTaskDefinition

- ea: `0x64ba0`
- end: `0x64c4f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::ResetExistingTaskDefinition`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x64a80`
- `0x87d10`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x645c0`
- `0x64ba0`
- `0x67c50`
- `0x67e80`
- `0x84ff0`
- `0x853e0`
- `0x85810`
- `0x85890`

## string_xrefs

- `0x64bd8`: `MessageTaskDoesNotExist`

## pseudocode

```c

```

## disassembly

```asm
0x64ba0  ldc.i4.0
0x64ba1  stloc.0
0x64ba2  ldarg.0
0x64ba3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64ba8  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ITriggerCollection Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition::get_Triggers()
0x64bad  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ITriggerCollection::Clear()
0x64bb2  ldarg.0
0x64bb3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureITaskDefinition
0x64bb8  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection Microsoft.Windows.ManagementUI.CombinedControls.ITaskDefinition::get_Actions()
0x64bbd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.IActionCollection::Clear()
0x64bc2  ldc.i4.1
0x64bc3  stloc.0
0x64bc4  leave    loc_64C4D
0x64bc9  stloc.1
0x64bca  ldarg.0
0x64bcb  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64bd0  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x64bd5  brtrue.s loc_64C03
0x64bd7  ldnull
0x64bd8  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x64bdd  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64be2  ldc.i4.2
0x64be3  newarr   [mscorlib]System.Object
0x64be8  dup
0x64be9  ldc.i4.0
0x64bea  ldarg.0
0x64beb  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64bf0  stelem.ref
0x64bf1  dup
0x64bf2  ldc.i4.1
0x64bf3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x64bf8  stelem.ref
0x64bf9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x64bfe  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x64c03  ldloc.1
0x64c04  callvirt instance string [mscorlib]System.Exception::get_Message()
0x64c09  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64c0e  leave.s  loc_64C4D
0x64c10  ldarg.0
0x64c11  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64c16  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x64c1b  brtrue.s loc_64C2C
0x64c1d  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x64c22  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x64c27  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x64c2c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x64c31  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x64c36  leave.s  loc_64C4D
0x64c38  stloc.2
0x64c39  ldarg.0
0x64c3a  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x64c3f  ldloc.2
0x64c40  ldarg.0
0x64c41  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x64c46  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x64c4b  leave.s  loc_64C4D
0x64c4d  ldloc.0
0x64c4e  ret
```
