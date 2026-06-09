# Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::ProcessDialogButton

- ea: `0x6d420`
- end: `0x6d4d8`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::ProcessDialogButton`
- size: `184`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d190`
- `0x6d620`
- `0x6d630`
- `0x6d640`
- `0x6d650`

## callees

- `0x12ed0`
- `0x132a0`
- `0x6cff0`
- `0x6d420`
- `0x6d4e0`
- `0x7cf40`

## string_xrefs

- `0x6d499`: `ApplicationTaskScheduler`
- `0x6d48c`: `UserQuestionEndInstanceTask`

## pseudocode

```c

```

## disassembly

```asm
0x6d420  ldarg.1
0x6d421  ldc.i4.1
0x6d422  sub
0x6d423  switch   loc_6D435, loc_6D47E, loc_6D485
0x6d434  ret
0x6d435  ldarg.0
0x6d436  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::listViewMain
0x6d43b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection [System.Windows.Forms]System.Windows.Forms.ListView::get_Items()
0x6d440  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView/ListViewItemCollection::Clear()
0x6d445  ldarg.0
0x6d446  ldarg.0
0x6d447  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::service
0x6d44c  call     instance bool Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::Initialize(class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService inService)
0x6d451  pop
0x6d452  ldarg.0
0x6d453  ldc.i4.0
0x6d454  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6d459  leave.s  loc_6D4D7
0x6d45b  pop
0x6d45c  ldarg.0
0x6d45d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::ownerView
0x6d462  brfalse.s loc_6D46F
0x6d464  ldarg.0
0x6d465  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::ownerView
0x6d46a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::HandleServiceUnavailableException()
0x6d46f  ldarg.0
0x6d470  ldc.i4.2
0x6d471  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6d476  ldarg.0
0x6d477  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::Close()
0x6d47c  leave.s  loc_6D4D7
0x6d47e  ldarg.0
0x6d47f  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::Close()
0x6d484  ret
0x6d485  ldarg.0
0x6d486  ldc.i4.0
0x6d487  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6d48c  ldstr    aUserquestionen// "UserQuestionEndInstanceTask"
0x6d491  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d496  stloc.0
0x6d497  ldarg.0
0x6d498  ldloc.0
0x6d499  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x6d49e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6d4a3  ldc.i4.0
0x6d4a4  call     valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult Microsoft.Windows.ManagementUI.CombinedControls.QueryMessage::QueryUser(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string message, string caption, bool allowCancel)
0x6d4a9  ldc.i4.6
0x6d4aa  bne.un.s loc_6D4D7
0x6d4ac  ldarg.0
0x6d4ad  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::EndTask()
0x6d4b2  leave.s  loc_6D4D7
0x6d4b4  pop
0x6d4b5  ldarg.0
0x6d4b6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::ownerView
0x6d4bb  brfalse.s loc_6D4C8
0x6d4bd  ldarg.0
0x6d4be  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl Microsoft.Windows.ManagementUI.CombinedControls.TaskInstancesDialog::ownerView
0x6d4c3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.BaseResultsControl::HandleServiceUnavailableException()
0x6d4c8  ldarg.0
0x6d4c9  ldc.i4.2
0x6d4ca  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6d4cf  ldarg.0
0x6d4d0  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::Close()
0x6d4d5  leave.s  loc_6D4D7
0x6d4d7  ret
```
