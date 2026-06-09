# Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::DeleteTask

- ea: `0x676c0`
- end: `0x6773a`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::DeleteTask`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x80e40`

## callees

- `0x12ed0`
- `0x133f0`
- `0x5d760`
- `0x5d7f0`
- `0x676c0`
- `0x67ec0`
- `0x83d20`

## string_xrefs

- `0x676ef`: `MessageTaskDoesNotExist`
- `0x67718`: `MessageTaskAccessDeleteException`

## pseudocode

```c

```

## disassembly

```asm
0x676c0  ldc.i4.0
0x676c1  stloc.0
0x676c2  ldarg.0
0x676c3  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::IsValid()
0x676c8  brfalse.s loc_67738
0x676ca  ldarg.0
0x676cb  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::secureITaskFolder
0x676d0  ldarg.1
0x676d1  ldc.i4.0
0x676d2  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ITaskFolder::DeleteTask(string name, int32 flags)
0x676d7  ldc.i4.1
0x676d8  stloc.0
0x676d9  leave.s  loc_67738
0x676db  pop
0x676dc  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x676e1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x676e6  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x676eb  leave.s  loc_67738
0x676ed  stloc.1
0x676ee  ldnull
0x676ef  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x676f4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x676f9  ldc.i4.2
0x676fa  newarr   [mscorlib]System.Object
0x676ff  dup
0x67700  ldc.i4.0
0x67701  ldarg.1
0x67702  stelem.ref
0x67703  dup
0x67704  ldc.i4.1
0x67705  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x6770a  stelem.ref
0x6770b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x67710  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x67715  ldloc.1
0x67716  throw
0x67717  pop
0x67718  ldstr    aMessagetaskacc_2// "MessageTaskAccessDeleteException"
0x6771d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x67722  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x67727  leave.s  loc_67738
0x67729  stloc.2
0x6772a  ldarg.0
0x6772b  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x67730  ldloc.2
0x67731  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e)
0x67736  leave.s  loc_67738
0x67738  ldloc.0
0x67739  ret
```
