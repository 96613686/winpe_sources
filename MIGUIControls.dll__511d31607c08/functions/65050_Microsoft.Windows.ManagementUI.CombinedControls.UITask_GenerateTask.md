# Microsoft.Windows.ManagementUI.CombinedControls.UITask::GenerateTask

- ea: `0x65050`
- end: `0x65227`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::GenerateTask`
- size: `471`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c3b0`
- `0x87d10`

## callees

- `0x12ed0`
- `0x133f0`
- `0x5d740`
- `0x5d760`
- `0x5d840`
- `0x5de70`
- `0x645c0`
- `0x64870`
- `0x64a80`
- `0x65050`
- `0x65790`
- `0x66e50`
- `0x66e60`
- `0x66ff0`
- `0x67020`
- `0x673c0`
- `0x67e80`

## string_xrefs

- `0x65173`: `MessageTaskDoesNotExist`
- `0x650af`: `MessageTaskSameNameAsFolder`
- `0x65153`: `MessageInvalidTaskName`
- `0x651a5`: `MessageInvalidTaskName`
- `0x651e5`: `MessageTaskAccessException`
- `0x651fb`: `MessageTaskAccessEditException`

## pseudocode

```c

```

## disassembly

```asm
0x65050  ldc.i4.0
0x65051  stloc.0
0x65052  ldc.i4.0
0x65053  stloc.1
0x65054  ldarg.0
0x65055  ldarg.0
0x65056  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.UITask::stringTaskName
0x6505b  callvirt instance string [mscorlib]System.String::Trim()
0x65060  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.UITask::stringTaskName
0x65065  ldarg.1
0x65066  brtrue.s loc_6506A
0x65068  ldc.i4.1
0x65069  stloc.1
0x6506a  ldarg.0
0x6506b  ldloc.1
0x6506c  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::SaveToTaskDefinition(bool isNewTask)
0x65071  stloc.0
0x65072  ldloc.0
0x65073  brfalse  loc_65103
0x65078  ldarg.0
0x65079  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_Parent()
0x6507e  isinst   Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder
0x65083  stloc.2
0x65084  ldnull
0x65085  stloc.3
0x65086  ldc.i4.0
0x65087  stloc.s  4
0x65089  br.s     loc_650C6
0x6508b  ldloc.2
0x6508c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolderList Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_ChildFolderList()
0x65091  ldloc.s  4
0x65093  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolderList::get_Item(int32 index)
0x65098  stloc.s  5
0x6509a  ldarg.0
0x6509b  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.UITask::stringTaskName
0x650a0  ldloc.s  5
0x650a2  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_Name()
0x650a7  ldc.i4.0
0x650a8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x650ad  brtrue.s loc_650C0
0x650af  ldstr    aMessagetasksam// "MessageTaskSameNameAsFolder"
0x650b4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x650b9  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x650be  ldc.i4.0
0x650bf  stloc.0
0x650c0  ldloc.s  4
0x650c2  ldc.i4.1
0x650c3  add
0x650c4  stloc.s  4
0x650c6  ldloc.s  4
0x650c8  ldloc.2
0x650c9  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolderList Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::get_ChildFolderList()
0x650ce  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolderList::get_Count()
0x650d3  blt.s    loc_6508B
0x650d5  ldloc.0
0x650d6  brfalse.s loc_65103
0x650d8  ldloc.2
0x650d9  ldarg.1
0x650da  ldarg.0
0x650db  ldarg.2
0x650dc  ldloc.1
0x650dd  ldloca.s 3
0x650df  ldarg.s  4
0x650e1  ldarg.s  5
0x650e3  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskFolder::RegisterTask(valuetype UserChoice newTask, class Microsoft.Windows.ManagementUI.CombinedControls.UITask task, bool commitTaskFlag, bool createTask, class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask& newIRegisteredTask, class [System.Windows.Forms]System.Windows.Forms.IWin32Window parentHandleForPasswordDialog, bool flagShowUserError)
0x650e8  stloc.0
0x650e9  ldloc.0
0x650ea  ldarg.3
0x650eb  and
0x650ec  brfalse.s loc_65103
0x650ee  ldarg.0
0x650ef  ldarg.0
0x650f0  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_Parent()
0x650f5  ldloc.3
0x650f6  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase parent, class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask task)
0x650fb  pop
0x650fc  ldarg.0
0x650fd  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITask::LoadFromTaskDefinition()
0x65102  pop
0x65103  leave    loc_65225
0x65108  stloc.s  6
0x6510a  ldarg.0
0x6510b  ldarg.s  4
0x6510d  ldloc.s  6
0x6510f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65114  ldarg.s  5
0x65116  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x6511b  leave    loc_65225
0x65120  stloc.s  7
0x65122  ldarg.0
0x65123  ldarg.s  4
0x65125  ldloc.s  7
0x65127  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6512c  ldc.i4.0
0x6512d  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x65132  leave    loc_65225
0x65137  stloc.s  8
0x65139  ldarg.1
0x6513a  ldc.i4.1
0x6513b  bne.un.s loc_65150
0x6513d  ldsfld   string [mscorlib]System.String::Empty
0x65142  ldarg.0
0x65143  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x65148  ldloc.s  8
0x6514a  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string, class [mscorlib]System.Exception)
0x6514f  throw
0x65150  ldarg.0
0x65151  ldarg.s  4
0x65153  ldstr    aMessageinvalid_4// "MessageInvalidTaskName"
0x65158  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6515d  ldarg.s  5
0x6515f  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x65164  leave    loc_65225
0x65169  stloc.s  9
0x6516b  ldarg.1
0x6516c  ldc.i4.1
0x6516d  bne.un.s loc_651A2
0x6516f  ldarg.0
0x65170  ldarg.s  4
0x65172  ldnull
0x65173  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x65178  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6517d  ldc.i4.2
0x6517e  newarr   [mscorlib]System.Object
0x65183  dup
0x65184  ldc.i4.0
0x65185  ldarg.0
0x65186  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x6518b  stelem.ref
0x6518c  dup
0x6518d  ldc.i4.1
0x6518e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x65193  stelem.ref
0x65194  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x65199  ldarg.s  5
0x6519b  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x651a0  br.s     loc_651B6
0x651a2  ldarg.0
0x651a3  ldarg.s  4
0x651a5  ldstr    aMessageinvalid_4// "MessageInvalidTaskName"
0x651aa  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x651af  ldarg.s  5
0x651b1  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x651b6  ldarg.0
0x651b7  ldarg.s  4
0x651b9  ldloc.s  9
0x651bb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x651c0  ldc.i4.0
0x651c1  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x651c6  leave.s  loc_65225
0x651c8  stloc.s  0xA
0x651ca  ldarg.0
0x651cb  ldarg.s  4
0x651cd  ldloc.s  0xA
0x651cf  ldarg.0
0x651d0  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x651d5  ldarg.s  5
0x651d7  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ProcessExternalErrors(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parentWindow, class [mscorlib]System.Runtime.InteropServices.ExternalException e, string taskName, bool showToUser)
0x651dc  leave.s  loc_65225
0x651de  pop
0x651df  ldarg.1
0x651e0  brtrue.s loc_651F8
0x651e2  ldarg.0
0x651e3  ldarg.s  4
0x651e5  ldstr    aMessagetaskacc// "MessageTaskAccessException"
0x651ea  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x651ef  ldarg.s  5
0x651f1  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x651f6  br.s     loc_6520C
0x651f8  ldarg.0
0x651f9  ldarg.s  4
0x651fb  ldstr    aMessagetaskacc_0// "MessageTaskAccessEditException"
0x65200  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x65205  ldarg.s  5
0x65207  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorMessage, bool showToUser)
0x6520c  leave.s  loc_65225
0x6520e  stloc.s  0xB
0x65210  ldarg.0
0x65211  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x65216  ldloc.s  0xB
0x65218  ldarg.0
0x65219  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x6521e  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x65223  leave.s  loc_65225
0x65225  ldloc.0
0x65226  ret
```
