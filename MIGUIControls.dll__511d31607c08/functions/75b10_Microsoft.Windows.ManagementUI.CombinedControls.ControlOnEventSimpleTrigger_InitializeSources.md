# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::InitializeSources

- ea: `0x75b10`
- end: `0x75c0c`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::InitializeSources`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x76090`

## callees

- `0x12ed0`
- `0x13440`
- `0x137d0`
- `0x1b7c0`
- `0x1b850`
- `0x4ea00`
- `0x64710`
- `0x67c80`
- `0x67ca0`
- `0x68690`
- `0x68760`
- `0x68980`
- `0x68990`
- `0x74de0`
- `0x75b10`

## string_xrefs

- `0x75bca`: `ApplicationTaskScheduler`
- `0x75beb`: `ApplicationTaskScheduler`
- `0x75bc0`: `MessageTaskCrimsonServiceNotRunning`
- `0x75be1`: `MessageTaskAccessViewEvents`

## pseudocode

```c

```

## disassembly

```asm
0x75b10  ldnull
0x75b11  stloc.0
0x75b12  ldarg.0
0x75b13  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Control::get_Cursor()
0x75b18  stloc.1
0x75b19  ldarg.0
0x75b1a  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_WaitCursor()
0x75b1f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x75b24  ldarg.0
0x75b25  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x75b2a  brfalse.s loc_75B5A
0x75b2c  ldarg.0
0x75b2d  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x75b32  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x75b37  stloc.2
0x75b38  ldarg.1
0x75b39  brfalse.s loc_75B5A
0x75b3b  ldarg.1
0x75b3c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig Microsoft.Windows.ManagementUI.CombinedControls.ChannelInfo::get_Config()
0x75b41  brfalse.s loc_75B5A
0x75b43  ldloc.2
0x75b44  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EventLogService()
0x75b49  ldarg.1
0x75b4a  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ChannelConfig Microsoft.Windows.ManagementUI.CombinedControls.ChannelInfo::get_Config()
0x75b4f  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.ConfigInstance::get_Path()
0x75b54  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.SourceInfoList Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService::GetSourcesForChannel(string channelName)
0x75b59  stloc.0
0x75b5a  ldloc.0
0x75b5b  brfalse.s loc_75B84
0x75b5d  ldc.i4.0
0x75b5e  stloc.3
0x75b5f  br.s     loc_75B7B
0x75b61  ldloc.0
0x75b62  ldloc.3
0x75b63  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.SourceInfo Microsoft.Windows.ManagementUI.CombinedControls.SourceInfoList::get_Item(int32 index)
0x75b68  stloc.s  4
0x75b6a  ldarg.0
0x75b6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxSource
0x75b70  ldloc.s  4
0x75b72  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x75b77  ldloc.3
0x75b78  ldc.i4.1
0x75b79  add
0x75b7a  stloc.3
0x75b7b  ldloc.3
0x75b7c  ldloc.0
0x75b7d  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.SourceInfoList::get_Count()
0x75b82  blt.s    loc_75B61
0x75b84  leave    loc_75C0B
0x75b89  stloc.s  5
0x75b8b  ldarg.0
0x75b8c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x75b91  brfalse.s loc_75C01
0x75b93  ldarg.0
0x75b94  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x75b99  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x75b9e  ldc.i4.0
0x75b9f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::set_IsConnectedToCrimson(bool value)
0x75ba4  ldarg.0
0x75ba5  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::accessMessageHasBeenDisplayed
0x75baa  brtrue.s loc_75C01
0x75bac  ldloc.s  5
0x75bae  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_ErrorNumber()
0x75bb3  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIException::ServiceNotAvailableError(int32 error)
0x75bb8  brfalse.s loc_75BDB
0x75bba  ldarg.0
0x75bbb  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x75bc0  ldstr    aMessagetaskcri// "MessageTaskCrimsonServiceNotRunning"
0x75bc5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75bca  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x75bcf  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75bd4  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x75bd9  br.s     loc_75BFA
0x75bdb  ldarg.0
0x75bdc  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x75be1  ldstr    aMessagetaskacc_7// "MessageTaskAccessViewEvents"
0x75be6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75beb  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x75bf0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75bf5  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x75bfa  ldarg.0
0x75bfb  ldc.i4.1
0x75bfc  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::accessMessageHasBeenDisplayed
0x75c01  leave.s  loc_75C0B
0x75c03  ldarg.0
0x75c04  ldloc.1
0x75c05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x75c0a  endfinally
0x75c0b  ret
```
