# Microsoft.Windows.ManagementUI.CombinedControls.UITask::RunTask

- ea: `0x655e0`
- end: `0x656e9`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UITask::RunTask`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x80ae0`

## callees

- `0x12ed0`
- `0x133f0`
- `0x13430`
- `0x5d760`
- `0x5d830`
- `0x5de60`
- `0x645c0`
- `0x64710`
- `0x655e0`
- `0x67c50`
- `0x67c70`
- `0x67e80`
- `0x83b90`

## string_xrefs

- `0x6562a`: `MessageTaskDoesNotExist`
- `0x6568f`: `MessageTaskAccessRunException`
- `0x656af`: `MessageNoRunTask`

## pseudocode

```c

```

## disassembly

```asm
0x655e0  ldc.i4.0
0x655e1  stloc.0
0x655e2  ldarg.0
0x655e3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x655e8  brfalse  loc_656E7
0x655ed  ldc.i4.2
0x655ee  stloc.1
0x655ef  ldc.i4   0x10002
0x655f4  ldarg.0
0x655f5  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x655fa  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_HighestVersion()
0x655ff  ble.s    loc_65603
0x65601  ldc.i4.0
0x65602  stloc.1
0x65603  nop
0x65604  ldarg.0
0x65605  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask Microsoft.Windows.ManagementUI.CombinedControls.UITask::secureIRegisteredTask
0x6560a  ldnull
0x6560b  ldloc.1
0x6560c  ldc.i4.m1
0x6560d  ldnull
0x6560e  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.IRunningTask Microsoft.Windows.ManagementUI.CombinedControls.IRegisteredTask::RunEx([in] [hasfieldmarshal] object parameters, valuetype Microsoft.Windows.ManagementUI.CombinedControls.TaskRunFlags flags, int32 sessionId, string user)
0x65613  pop
0x65614  ldc.i4.1
0x65615  stloc.0
0x65616  leave    loc_656E7
0x6561b  stloc.2
0x6561c  ldarg.0
0x6561d  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x65622  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x65627  brtrue.s loc_65655
0x65629  ldnull
0x6562a  ldstr    aMessagetaskdoe// "MessageTaskDoesNotExist"
0x6562f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x65634  ldc.i4.2
0x65635  newarr   [mscorlib]System.Object
0x6563a  dup
0x6563b  ldc.i4.0
0x6563c  ldarg.0
0x6563d  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x65642  stelem.ref
0x65643  dup
0x65644  ldc.i4.1
0x65645  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x6564a  stelem.ref
0x6564b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x65650  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x65655  ldloc.2
0x65656  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6565b  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x65660  leave    loc_656E7
0x65665  ldarg.0
0x65666  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x6566b  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_IsShuttingDown()
0x65670  brtrue.s loc_65681
0x65672  ldstr    aMessagefoldern// "MessageFolderNotFound"
0x65677  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6567c  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x65681  callvirt instance string [mscorlib]System.Exception::get_Message()
0x65686  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::SystemError(string errorString)
0x6568b  leave.s  loc_656E7
0x6568d  pop
0x6568e  ldarg.0
0x6568f  ldstr    aMessagetaskacc_1// "MessageTaskAccessRunException"
0x65694  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x65699  ldc.i4.1
0x6569a  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ShowErrorMessage(string errorMessage, bool showToUser)
0x6569f  leave.s  loc_656E7
0x656a1  stloc.3
0x656a2  ldloc.3
0x656a3  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x656a8  ldc.i4   0x80070032
0x656ad  bne.un.s loc_656C0
0x656af  ldstr    aMessagenorunta// "MessageNoRunTask"
0x656b4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x656b9  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x656be  br.s     loc_656CE
0x656c0  ldarg.0
0x656c1  ldloc.3
0x656c2  ldarg.0
0x656c3  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x656c8  ldc.i4.1
0x656c9  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::ProcessExternalErrors(class [mscorlib]System.Runtime.InteropServices.ExternalException e, string taskName, bool showToUser)
0x656ce  leave.s  loc_656E7
0x656d0  stloc.s  4
0x656d2  ldarg.0
0x656d3  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x656d8  ldloc.s  4
0x656da  ldarg.0
0x656db  call     instance string Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_Name()
0x656e0  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::ProcessServiceErrors(class [mscorlib]System.Exception e, string taskName)
0x656e5  leave.s  loc_656E7
0x656e7  ldloc.0
0x656e8  ret
```
