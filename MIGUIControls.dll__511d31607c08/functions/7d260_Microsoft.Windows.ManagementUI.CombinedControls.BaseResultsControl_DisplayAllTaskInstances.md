# Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::DisplayAllTaskInstances

- ea: `0x7d260`
- end: `0x7d2e4`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::DisplayAllTaskInstances`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x13000`
- `0x133f0`
- `0x1b4d0`
- `0x5d760`
- `0x5d7a0`
- `0x6cf70`
- `0x6cf90`
- `0x6cfa0`
- `0x6cff0`
- `0x7cd80`
- `0x7cf40`
- `0x7d260`

## string_xrefs

- `0x7d27d`: `AllTaskInstances`
- `0x7d2b8`: `MessageTaskInstancesNotSupported`

## pseudocode

```c

```

## disassembly

```asm
0x7d260  ldc.i4.0
0x7d261  stloc.0
0x7d262  ldc.i4.0
0x7d263  stloc.1
0x7d264  ldnull
0x7d265  stloc.2
0x7d266  ldc.i4   0xEDB
0x7d26b  call     void Microsoft.Windows.ManagementUI.CombinedControls.SnapInFeedback::IncrementGlobalDatapoint(valuetype Microsoft.Windows.ManagementUI.CombinedControls.FeedbackDatapoint datapoint)
0x7d270  ldarg.1
0x7d271  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x7d276  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_RunningInstancesAreSupported()
0x7d27b  brfalse.s loc_7D2B8
0x7d27d  ldstr    aAlltaskinstanc// "AllTaskInstances"
0x7d282  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d287  ldarg.0
0x7d288  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::get_IsShowHiddenTasks()
0x7d28d  ldarg.0
0x7d28e  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::.ctor(string titleVersion, bool inShowHiddenTasks, class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl inOwnerView)
0x7d293  stloc.2
0x7d294  ldloc.2
0x7d295  ldarg.1
0x7d296  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITaskBase::get_UITaskService()
0x7d29b  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService inService)
0x7d2a0  brfalse.s loc_7D2C7
0x7d2a2  ldloc.2
0x7d2a3  callvirt instance bool Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::TaskAlreadyLoaded()
0x7d2a8  brtrue.s loc_7D2B2
0x7d2aa  ldloc.2
0x7d2ab  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::ShowModelessDialog(class [System.Windows.Forms]System.Windows.Forms.Form dialog)
0x7d2b0  br.s     loc_7D2B4
0x7d2b2  ldc.i4.1
0x7d2b3  stloc.1
0x7d2b4  ldc.i4.1
0x7d2b5  stloc.0
0x7d2b6  br.s     loc_7D2C7
0x7d2b8  ldstr    aMessagetaskins// "MessageTaskInstancesNotSupported"
0x7d2bd  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x7d2c2  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(string errorString)
0x7d2c7  leave.s  loc_7D2D4
0x7d2c9  pop
0x7d2ca  ldc.i4.0
0x7d2cb  stloc.0
0x7d2cc  ldarg.0
0x7d2cd  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::HandleServiceUnavailableException()
0x7d2d2  leave.s  loc_7D2D4
0x7d2d4  ldloc.2
0x7d2d5  ldnull
0x7d2d6  cgt.un
0x7d2d8  ldloc.1
0x7d2d9  and
0x7d2da  brfalse.s loc_7D2E2
0x7d2dc  ldloc.2
0x7d2dd  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::DisposeDialog()
0x7d2e2  ldloc.0
0x7d2e3  ret
```
