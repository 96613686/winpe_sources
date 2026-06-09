# Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::EndTaskInstance

- ea: `0x683d0`
- end: `0x68505`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::EndTaskInstance`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d4e0`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x5d830`
- `0x5de60`
- `0x67c50`
- `0x67ec0`
- `0x682f0`
- `0x683d0`
- `0x83a60`
- `0x83a70`
- `0x83ab0`
- `0x83af0`
- `0x83b00`

## string_xrefs

- `0x68451`: `MessageTaskDoesNotExist`
- `0x684b0`: `MessageTaskAccessStopException`

## pseudocode

```c

```

## disassembly

```asm
0x683d0  ldc.i4.0
0x683d1  stloc.0
0x683d2  ldnull
0x683d3  stloc.1
0x683d4  ldnull
0x683d5  stloc.2
0x683d6  ldc.i4.0
0x683d7  stloc.3
0x683d8  ldarg.2
0x683d9  brfalse.s loc_683DD
0x683db  ldc.i4.1
0x683dc  stloc.3
0x683dd  ldsfld   string [mscorlib]System.String::Empty
0x683e2  stloc.s  4
0x683e4  ldarg.0
0x683e5  ldloc.3
0x683e6  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.IRunningTaskCollection Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::GetRunningTasks(valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskEnumFlags flags)
0x683eb  stloc.1
0x683ec  ldloc.1
0x683ed  brfalse.s loc_6843C
0x683ef  ldc.i4.1
0x683f0  stloc.s  5
0x683f2  br.s     loc_68432
0x683f4  ldloc.1
0x683f5  ldloc.s  5
0x683f7  box      [mscorlib]System.Int32
0x683fc  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IRunningTask Microsoft.Windows.ManagementUI.CombinedControls.IRunningTaskCollection::GetItem(object index)
0x68401  stloc.2
0x68402  ldloc.2
0x68403  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IRunningTask::get_Name()
0x68408  stloc.s  4
0x6840a  ldarg.1
0x6840b  ldloc.2
0x6840c  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.IRunningTask::get_InstanceGuid()
0x68411  ldc.i4.0
0x68412  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x68417  brtrue.s loc_68423
0x68419  ldloc.2
0x6841a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.IRunningTask::Stop()
0x6841f  ldc.i4.1
0x68420  stloc.0
0x68421  br.s     loc_6843C
0x68423  ldloc.2
0x68424  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x68429  pop
0x6842a  ldnull
0x6842b  stloc.2
0x6842c  ldloc.s  5
0x6842e  ldc.i4.1
0x6842f  add
0x68430  stloc.s  5
0x68432  ldloc.s  5
0x68434  ldloc.1
0x68435  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.IRunningTaskCollection::get_Count()
0x6843a  ble.s    loc_683F4
0x6843c  leave    loc_684EF
0x68441  stloc.s  6
0x68443  ldarg.0
0x68444  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x68449  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x6844e  brtrue.s loc_68478
0x68450  ldnull
0x68451  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x68456  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6845b  ldc.i4.2
0x6845c  newarr   [mscorlib]System.Object
0x68461  dup
0x68462  ldc.i4.0
0x68463  ldloc.s  4
0x68465  stelem.ref
0x68466  dup
0x68467  ldc.i4.1
0x68468  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x6846d  stelem.ref
0x6846e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x68473  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x68478  ldloc.s  6
0x6847a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6847f  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x68484  leave.s  loc_684EF
0x68486  ldarg.0
0x68487  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x6848c  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x68491  brtrue.s loc_684A2
0x68493  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x68498  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6849d  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x684a2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x684a7  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x684ac  leave.s  loc_684EF
0x684ae  pop
0x684af  ldarg.0
0x684b0  ldstr    aMessagetaskacc_4// "MessageTaskAccessStopException"
0x684b5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x684ba  ldc.i4.1
0x684bb  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(string errorMessage, bool showToUser)
0x684c0  leave.s  loc_684EF
0x684c2  stloc.s  7
0x684c4  ldc.i4   0x8004130B
0x684c9  ldloc.s  7
0x684cb  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x684d0  bne.un.s loc_684D6
0x684d2  ldc.i4.1
0x684d3  stloc.0
0x684d4  br.s     loc_684E1
0x684d6  ldarg.0
0x684d7  ldloc.s  7
0x684d9  ldloc.s  4
0x684db  ldc.i4.1
0x684dc  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ProcessExternalErrors(class [mscorlib]System.Runtime.InteropServices.ExternalException e, string taskName, bool showToUser)
0x684e1  leave.s  loc_684EF
0x684e3  stloc.s  8
0x684e5  ldarg.0
0x684e6  ldloc.s  8
0x684e8  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e)
0x684ed  leave.s  loc_684EF
0x684ef  ldloc.2
0x684f0  brfalse.s loc_684F9
0x684f2  ldloc.2
0x684f3  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x684f8  pop
0x684f9  ldloc.1
0x684fa  brfalse.s loc_68503
0x684fc  ldloc.1
0x684fd  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::ReleaseComObject(object)
0x68502  pop
0x68503  ldloc.0
0x68504  ret
```
