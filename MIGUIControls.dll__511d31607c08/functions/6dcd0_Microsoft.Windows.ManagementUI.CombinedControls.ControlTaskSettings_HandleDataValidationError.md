# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::HandleDataValidationError

- ea: `0x6dcd0`
- end: `0x6dd7f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::HandleDataValidationError`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x12ed0`
- `0x13440`
- `0x135f0`
- `0x136f0`
- `0x1ba30`
- `0x1ba50`
- `0x6dcd0`

## string_xrefs

- `0x6dcf4`: `ApplicationTaskScheduler`
- `0x6dcd8`: `UITaskAdvancedSettings`
- `0x6dd63`: `DeleteExpiredTaskAfter`

## pseudocode

```c

```

## disassembly

```asm
0x6dcd0  ldc.i4.0
0x6dcd1  stloc.0
0x6dcd2  ldarg.1
0x6dcd3  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_SectionName()
0x6dcd8  ldstr    aUitaskadvanced// "UITaskAdvancedSettings"
0x6dcdd  ldc.i4.4
0x6dcde  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6dce3  brtrue   loc_6DD7D
0x6dce8  ldarg.0
0x6dce9  call     instance class [System.Windows.Forms]System.Windows.Forms.Form [System.Windows.Forms]System.Windows.Forms.ContainerControl::get_ParentForm()
0x6dcee  ldarg.1
0x6dcef  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6dcf4  ldstr    aApplicationtas// "ApplicationTaskScheduler"
0x6dcf9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x6dcfe  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::UserError(class [System.Windows.Forms]System.Windows.Forms.IWin32Window parent, string errorString, string caption)
0x6dd03  ldarg.1
0x6dd04  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_PropertyName()
0x6dd09  ldstr    aRestartinterva// "RestartInterval"
0x6dd0e  ldc.i4.4
0x6dd0f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6dd14  brtrue.s loc_6DD21
0x6dd16  ldarg.0
0x6dd17  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerRestartInterval
0x6dd1c  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SelectTimeSpanControl(class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker ctl)
0x6dd21  ldarg.1
0x6dd22  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_PropertyName()
0x6dd27  ldstr    aRestartcount// "RestartCount"
0x6dd2c  ldc.i4.4
0x6dd2d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6dd32  brtrue.s loc_6DD3F
0x6dd34  ldarg.0
0x6dd35  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::textBoxRestartCount
0x6dd3a  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SelectTextControl(class [System.Windows.Forms]System.Windows.Forms.TextBoxBase ctl)
0x6dd3f  ldarg.1
0x6dd40  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_PropertyName()
0x6dd45  ldstr    aExecutiontimel// "ExecutionTimeLimit"
0x6dd4a  ldc.i4.4
0x6dd4b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6dd50  brtrue.s loc_6DD5D
0x6dd52  ldarg.0
0x6dd53  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerExecutionLimit
0x6dd58  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SelectTimeSpanControl(class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker ctl)
0x6dd5d  ldarg.1
0x6dd5e  callvirt instance string Microsoft.Windows.ManagementUI.CombinedControls.UIValidationException::get_PropertyName()
0x6dd63  ldstr    aDeleteexpiredt// "DeleteExpiredTaskAfter"
0x6dd68  ldc.i4.4
0x6dd69  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6dd6e  brtrue.s loc_6DD7B
0x6dd70  ldarg.0
0x6dd71  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerDeleteExpiredTaskAfter
0x6dd76  call     void Microsoft.Windows.ManagementUI.CombinedControls.UIControlProcessing::SelectTimeSpanControl(class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker ctl)
0x6dd7b  ldc.i4.1
0x6dd7c  stloc.0
0x6dd7d  ldloc.0
0x6dd7e  ret
```
