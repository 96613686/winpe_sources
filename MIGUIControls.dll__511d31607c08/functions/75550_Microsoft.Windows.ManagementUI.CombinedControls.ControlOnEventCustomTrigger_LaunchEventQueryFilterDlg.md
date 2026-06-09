# Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventCustomTrigger::LaunchEventQueryFilterDlg

- ea: `0x75550`
- end: `0x7566d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventCustomTrigger::LaunchEventQueryFilterDlg`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x75680`

## callees

- `0x12ed0`
- `0x13440`
- `0x145d0`
- `0x1b7c0`
- `0x1b850`
- `0x4d810`
- `0x5a910`
- `0x5a980`
- `0x5aba0`
- `0x5ac00`
- `0x5ac20`
- `0x5acc0`
- `0x5acf0`
- `0x64710`
- `0x67c80`
- `0x67ca0`
- `0x685f0`
- `0x74dd0`
- `0x74de0`
- `0x75550`
- `0x75670`

## string_xrefs

- `0x75628`: `ApplicationTaskScheduler`
- `0x75649`: `ApplicationTaskScheduler`
- `0x7561e`: `MessageTaskCrimsonServiceNotRunning`
- `0x7563f`: `MessageTaskAccessViewEvents`

## pseudocode

```c

```

## disassembly

```asm
0x75550  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::.ctor()
0x75555  stloc.0
0x75556  ldarg.0
0x75557  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x7555c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x75561  stloc.1
0x75562  ldloc.0
0x75563  brfalse  loc_75661
0x75568  ldloc.0
0x75569  ldc.i4.1
0x7556a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_IsOwnedByTaskScheduler(bool value)
0x7556f  ldloc.0
0x75570  ldloc.1
0x75571  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_EventLogService()
0x75576  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext Microsoft.Windows.ManagementUI.CombinedControls.UIEventLogService::get_Context()
0x7557b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_Context(class Microsoft.Windows.ManagementUI.CombinedControls.ViewerContext value)
0x75580  ldloc.0
0x75581  ldc.i4.0
0x75582  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_IncludeDirectAndExternalLogs(bool value)
0x75587  ldloc.0
0x75588  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::InitializeView()
0x7558d  ldarg.0
0x7558e  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventCustomTrigger::queryToUse
0x75593  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75598  brtrue.s loc_755BF
0x7559a  ldarg.0
0x7559b  ldfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventCustomTrigger::queryToUse
0x755a0  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.EventQuery::.ctor(string evtQry)
0x755a5  stloc.2
0x755a6  ldloc.0
0x755a7  ldstr    aTitleeditevent// "TitleEditEventFilter"
0x755ac  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x755b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x755b6  ldloc.0
0x755b7  ldloc.2
0x755b8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::set_Query(class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery value)
0x755bd  br.s     loc_755CF
0x755bf  ldloc.0
0x755c0  ldstr    aTitleneweventf// "TitleNewEventFilter"
0x755c5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x755ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x755cf  ldloc.0
0x755d0  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.Form::ShowDialog()
0x755d5  ldc.i4.1
0x755d6  bne.un.s loc_755EF
0x755d8  ldarg.0
0x755d9  ldloc.0
0x755da  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.EventQuery Microsoft.Windows.ManagementUI.CombinedControls.QueryFilterDlg::get_Query()
0x755df  callvirt instance string [mscorlib]System.Object::ToString()
0x755e4  stfld    string Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventCustomTrigger::queryToUse
0x755e9  ldarg.0
0x755ea  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventCustomTrigger::InitializeCustomQuery()
0x755ef  leave.s  loc_75661
0x755f1  stloc.3
0x755f2  ldarg.0
0x755f3  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_CurrentTask()
0x755f8  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x755fd  ldc.i4.0
0x755fe  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::set_IsConnectedToCrimson(bool value)
0x75603  ldarg.0
0x75604  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventCustomTrigger::accessMessageHasBeenDisplayed
0x75609  brtrue.s loc_7565F
0x7560b  ldloc.3
0x7560c  callvirt instance int32 Microsoft.Windows.ManagementUI.CombinedControls.UIException::get_ErrorNumber()
0x75611  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIException::ServiceNotAvailableError(int32 error)
0x75616  brfalse.s loc_75639
0x75618  ldarg.0
0x75619  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x7561e  ldstr    aMessagetaskcri// "MessageTaskCrimsonServiceNotRunning"
0x75623  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75628  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x7562d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75632  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x75637  br.s     loc_75658
0x75639  ldarg.0
0x7563a  call     instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x7563f  ldstr    aMessagetaskacc_7// "MessageTaskAccessViewEvents"
0x75644  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75649  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x7564e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x75653  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x75658  ldarg.0
0x75659  ldc.i4.1
0x7565a  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.ControlOnEventCustomTrigger::accessMessageHasBeenDisplayed
0x7565f  leave.s  loc_75661
0x75661  ldarg.0
0x75662  call     instance class Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataHandler Microsoft.Windows.ManagementUI.CombinedControls.BaseUITriggerControl::get_RequiredData()
0x75667  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.RequiredDataHandler::InformParent()
0x7566c  ret
```
