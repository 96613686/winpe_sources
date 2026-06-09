# Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::GetUITask

- ea: `0x672b0`
- end: `0x673bb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::GetUITask`
- size: `267`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x64830`
- `0x6bd20`
- `0x878d0`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x5d7f0`
- `0x64780`
- `0x672b0`
- `0x67ec0`
- `0x83d00`

## string_xrefs

- `0x6730b`: `MessageTaskDoesNotExist`
- `0x67373`: `MessageTaskInUse`

## pseudocode

```c

```

## disassembly

```asm
0x672b0  ldnull
0x672b1  stloc.0
0x672b2  ldarg.0
0x672b3  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::IsValid()
0x672b8  brfalse  loc_673B9
0x672bd  ldnull
0x672be  stloc.1
0x672bf  ldarg.1
0x672c0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x672c5  brtrue.s loc_672DE
0x672c7  ldarg.0
0x672c8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::secureITaskFolder
0x672cd  ldarg.1
0x672ce  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.ITaskFolder::GetTask(string path)
0x672d3  stloc.1
0x672d4  ldarg.0
0x672d5  ldloc.1
0x672d6  call     class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetUITask(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase parent, class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask task)
0x672db  stloc.0
0x672dc  br.s     loc_672E6
0x672de  ldarg.0
0x672df  ldnull
0x672e0  call     class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.UITask::GetUITask(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase parent, class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask task)
0x672e5  stloc.0
0x672e6  leave    loc_673B9
0x672eb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x672f0  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x672f5  leave    loc_673B9
0x672fa  callvirt instance string [mscorlib]System.Exception::get_Message()
0x672ff  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x67304  leave    loc_673B9
0x67309  stloc.2
0x6730a  ldnull
0x6730b  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x67310  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x67315  ldc.i4.2
0x67316  newarr   [mscorlib]System.Object
0x6731b  dup
0x6731c  ldc.i4.0
0x6731d  ldarg.1
0x6731e  stelem.ref
0x6731f  dup
0x67320  ldc.i4.1
0x67321  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x67326  stelem.ref
0x67327  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6732c  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x67331  ldloc.2
0x67332  callvirt instance string [mscorlib]System.Exception::get_Message()
0x67337  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x6733c  leave.s  loc_673B9
0x6733e  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x67343  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x67348  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x6734d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x67352  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x67357  leave.s  loc_673B9
0x67359  stloc.3
0x6735a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6735f  ldtoken  [mscorlib]System.String
0x67364  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67369  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x6736e  castclass [mscorlib]System.IFormatProvider
0x67373  ldstr    aMessagetaskinu// "MessageTaskInUse"
0x67378  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6737d  ldc.i4.2
0x6737e  newarr   [mscorlib]System.Object
0x67383  dup
0x67384  ldc.i4.0
0x67385  ldarg.1
0x67386  stelem.ref
0x67387  dup
0x67388  ldc.i4.1
0x67389  ldloc.3
0x6738a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6738f  stelem.ref
0x67390  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x67395  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x6739a  leave.s  loc_673B9
0x6739c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x673a1  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x673a6  leave.s  loc_673B9
0x673a8  stloc.s  4
0x673aa  ldarg.0
0x673ab  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x673b0  ldloc.s  4
0x673b2  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e)
0x673b7  leave.s  loc_673B9
0x673b9  ldloc.0
0x673ba  ret
```
