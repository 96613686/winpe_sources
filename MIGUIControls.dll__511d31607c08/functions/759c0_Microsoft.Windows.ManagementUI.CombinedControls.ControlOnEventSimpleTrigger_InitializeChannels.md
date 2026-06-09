# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::InitializeChannels

- ea: `0x759c0`
- end: `0x75af6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::InitializeChannels`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x75840`

## callees

- `0x12ed0`
- `0x13440`
- `0x137d0`
- `0x137e0`
- `0x1b7c0`
- `0x1b850`
- `0x64710`
- `0x67c80`
- `0x67ca0`
- `0x685d0`
- `0x68830`
- `0x68840`
- `0x74de0`
- `0x759c0`

## string_xrefs

- `0x75a64`: `ApplicationTaskScheduler`
- `0x75abb`: `ApplicationTaskScheduler`
- `0x75adc`: `ApplicationTaskScheduler`
- `0x75ad2`: `MessageTaskAccessViewEvents`
- `0x75a5a`: `MessageTaskCrimsonServiceNotRunningMissingEventFields`
- `0x75ab1`: `MessageTaskCrimsonServiceNotRunningMissingEventFields`

## pseudocode

```c

```

## disassembly

```asm
0x759c0  ldc.i4.0
0x759c1  stloc.0
0x759c2  ldnull
0x759c3  stloc.1
0x759c4  ldarg.0
0x759c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x759ca  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::ClearComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo)
0x759cf  ldarg.0
0x759d0  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x759d5  brfalse.s loc_759ED
0x759d7  ldarg.0
0x759d8  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x759dd  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x759e2  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EventLogService()
0x759e7  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ChannelInfoList Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService::get_ChannelList()
0x759ec  stloc.1
0x759ed  ldloc.1
0x759ee  brfalse.s loc_75A33
0x759f0  ldarg.0
0x759f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x759f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::BeginUpdate()
0x759fb  ldc.i4.0
0x759fc  stloc.2
0x759fd  br.s     loc_75A1D
0x759ff  ldloc.1
0x75a00  ldloc.2
0x75a01  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ChannelInfo Microsoft.Windows.ManagementUI.CombinedControls.ChannelInfoList::get_Item(int32 index)
0x75a06  pop
0x75a07  ldarg.0
0x75a08  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75a0d  ldloc.1
0x75a0e  ldloc.2
0x75a0f  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ChannelInfo Microsoft.Windows.ManagementUI.CombinedControls.ChannelInfoList::get_Item(int32 index)
0x75a14  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::AddToComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox combo, object objectToAdd)
0x75a19  ldloc.2
0x75a1a  ldc.i4.1
0x75a1b  add
0x75a1c  stloc.2
0x75a1d  ldloc.2
0x75a1e  ldloc.1
0x75a1f  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.ChannelInfoList::get_Count()
0x75a24  blt.s    loc_759FF
0x75a26  ldarg.0
0x75a27  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::comboBoxLog
0x75a2c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::EndUpdate()
0x75a31  br.s     loc_75A7A
0x75a33  ldarg.0
0x75a34  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x75a39  brfalse.s loc_75A4C
0x75a3b  ldarg.0
0x75a3c  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x75a41  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x75a46  ldc.i4.0
0x75a47  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::set_IsConnectedToCrimson(bool value)
0x75a4c  ldarg.0
0x75a4d  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::missingSystemMessageHasBeenDisplayed
0x75a52  brtrue.s loc_75A7A
0x75a54  ldarg.0
0x75a55  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x75a5a  ldstr    aMessagetaskcri_0// "MessageTaskCrimsonServiceNotRunningMiss"...
0x75a5f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75a64  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x75a69  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75a6e  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x75a73  ldarg.0
0x75a74  ldc.i4.1
0x75a75  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::missingSystemMessageHasBeenDisplayed
0x75a7a  leave.s  loc_75AF4
0x75a7c  stloc.3
0x75a7d  ldarg.0
0x75a7e  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x75a83  brfalse.s loc_75AF2
0x75a85  ldarg.0
0x75a86  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x75a8b  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x75a90  ldc.i4.0
0x75a91  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::set_IsConnectedToCrimson(bool value)
0x75a96  ldarg.0
0x75a97  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::missingSystemMessageHasBeenDisplayed
0x75a9c  brtrue.s loc_75AF2
0x75a9e  ldloc.3
0x75a9f  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_ErrorNumber()
0x75aa4  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIException::ServiceNotAvailableError(int32 error)
0x75aa9  brfalse.s loc_75ACC
0x75aab  ldarg.0
0x75aac  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x75ab1  ldstr    aMessagetaskcri_0// "MessageTaskCrimsonServiceNotRunningMiss"...
0x75ab6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75abb  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x75ac0  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75ac5  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x75aca  br.s     loc_75AEB
0x75acc  ldarg.0
0x75acd  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x75ad2  ldstr    aMessagetaskacc_7// "MessageTaskAccessViewEvents"
0x75ad7  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75adc  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x75ae1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75ae6  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x75aeb  ldarg.0
0x75aec  ldc.i4.1
0x75aed  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventSimpleTrigger::missingSystemMessageHasBeenDisplayed
0x75af2  leave.s  loc_75AF4
0x75af4  ldloc.0
0x75af5  ret
```
