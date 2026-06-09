# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::HandleDataValidationError

- ea: `0x722f0`
- end: `0x7239f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::HandleDataValidationError`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x13440`
- `0x135f0`
- `0x13830`
- `0x1ba30`
- `0x1ba50`
- `0x64710`
- `0x67bb0`
- `0x722f0`
- `0x72a70`

## string_xrefs

- `0x72327`: `ApplicationTaskScheduler`
- `0x722f8`: `UITaskRegistrationInfo`
- `0x7235a`: `Compatibility`
- `0x7230b`: `UITaskUser`
- `0x72378`: `TaskLogonType`

## pseudocode

```c

```

## disassembly

```asm
0x722f0  ldc.i4.0
0x722f1  stloc.0
0x722f2  ldarg.1
0x722f3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_SectionName()
0x722f8  ldstr    aUitaskregistra// "UITaskRegistrationInfo"
0x722fd  ldc.i4.4
0x722fe  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x72303  brfalse.s loc_7231B
0x72305  ldarg.1
0x72306  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_SectionName()
0x7230b  ldstr    aUitaskuser// "UITaskUser"
0x72310  ldc.i4.4
0x72311  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x72316  brtrue   loc_7239D
0x7231b  ldarg.0
0x7231c  call     instance class [System.Windows.Forms]System.Windows.Forms.Form [System.Windows.Forms]System.Windows.Forms.ContainerControl::get_ParentForm()
0x72321  ldarg.1
0x72322  callvirt instance string [mscorlib]System.Exception::get_Message()
0x72327  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x7232c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x72331  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x72336  ldarg.1
0x72337  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_PropertyName()
0x7233c  ldstr    aName// "Name"
0x72341  ldc.i4.4
0x72342  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x72347  brtrue.s loc_72354
0x72349  ldarg.0
0x7234a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName
0x7234f  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SelectTextControl(class [System.Windows.Forms]System.Windows.Forms.TextBoxBase ctl)
0x72354  ldarg.1
0x72355  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_PropertyName()
0x7235a  ldstr    aCompatibility// "Compatibility"
0x7235f  ldc.i4.4
0x72360  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x72365  brtrue.s loc_72372
0x72367  ldarg.0
0x72368  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x7236d  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SelectComboBox(class [System.Windows.Forms]System.Windows.Forms.ComboBox ctl)
0x72372  ldarg.1
0x72373  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_PropertyName()
0x72378  ldstr    aTasklogontype// "TaskLogonType"
0x7237d  ldc.i4.4
0x7237e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x72383  brtrue.s loc_7239B
0x72385  ldarg.0
0x72386  ldarg.0
0x72387  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.UITask Microsoft.Windows.ManagementUI.CombinedControls.BasePropertyControl::currentTask
0x7238c  callvirt instance class Microsoft.Windows.ManagementUI.CombinedControls.UITaskService Microsoft.Windows.ManagementUI.CombinedControls.UITask::get_TaskService()
0x72391  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UITaskService::get_ComputerName()
0x72396  call     instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::InvokeObjectPicker(string targetComputerName)
0x7239b  ldc.i4.1
0x7239c  stloc.0
0x7239d  ldloc.0
0x7239e  ret
```
