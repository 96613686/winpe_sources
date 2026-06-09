# Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::InitializeComponent

- ea: `0x7ba60`
- end: `0x7c259`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::InitializeComponent`
- size: `2041`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7aec0`

## callees

- `0x187d0`
- `0x187e0`
- `0x18ae0`
- `0x18b10`

## string_xrefs

- `0x7bdba`: `checkBoxDelayTask`
- `0x7bdca`: `checkBoxDelayTask`
- `0x7bf42`: `checkBoxDelayTaskRandomly`
- `0x7bf52`: `checkBoxDelayTaskRandomly`

## pseudocode

```c

```

## disassembly

```asm
0x7ba60  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings
0x7ba65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7ba6a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x7ba6f  ldarg.0
0x7ba70  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x7ba75  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDelay
0x7ba7a  ldarg.0
0x7ba7b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x7ba80  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRandomDelay
0x7ba85  ldarg.0
0x7ba86  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x7ba8b  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionInterval
0x7ba90  ldarg.0
0x7ba91  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x7ba96  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDuration
0x7ba9b  ldarg.0
0x7ba9c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x7baa1  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerExecutionLimit
0x7baa6  ldarg.0
0x7baa7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7baac  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxExecutionLimit
0x7bab1  ldarg.0
0x7bab2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7bab7  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxStopAtDurationEnd
0x7babc  ldarg.0
0x7babd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7bac2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::labelDurationOf
0x7bac7  ldarg.0
0x7bac8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7bacd  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxRepetitionInterval
0x7bad2  ldarg.0
0x7bad3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7bad8  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxDelayTask
0x7badd  ldarg.0
0x7bade  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7bae3  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxActiveOn
0x7bae8  ldarg.0
0x7bae9  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker::.ctor()
0x7baee  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::dateTimePickerActiveOn
0x7baf3  ldarg.0
0x7baf4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7baf9  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxExpire
0x7bafe  ldarg.0
0x7baff  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker::.ctor()
0x7bb04  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::dateTimePickerExpireOn
0x7bb09  ldarg.0
0x7bb0a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7bb0f  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxDelayTaskRandomly
0x7bb14  ldarg.0
0x7bb15  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7bb1a  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxEnabled
0x7bb1f  ldarg.0
0x7bb20  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x7bb25  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bb2a  ldarg.0
0x7bb2b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7bb30  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxIsActivateOnUtc
0x7bb35  ldarg.0
0x7bb36  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7bb3b  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxIsExpireUtc
0x7bb40  ldarg.0
0x7bb41  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bb46  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7bb4b  ldarg.0
0x7bb4c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7bb51  ldarg.0
0x7bb52  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bb57  ldarg.0
0x7bb58  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDelay
0x7bb5d  ldc.i4.2
0x7bb5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bb63  dup
0x7bb64  ldarg.0
0x7bb65  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDelay
0x7bb6a  ldstr    aTimespanpicker_5// "timeSpanPickerRepetitionDelay"
0x7bb6f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bb74  ldarg.0
0x7bb75  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDelay
0x7bb7a  ldstr    aTimespanpicker_5// "timeSpanPickerRepetitionDelay"
0x7bb7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bb84  ldarg.0
0x7bb85  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDelay
0x7bb8a  ldstr    a000300// "00:03:00"
0x7bb8f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x7bb94  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x7bb99  ldarg.0
0x7bb9a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bb9f  ldarg.0
0x7bba0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRandomDelay
0x7bba5  ldc.i4.2
0x7bba6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bbab  dup
0x7bbac  ldarg.0
0x7bbad  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRandomDelay
0x7bbb2  ldstr    aTimespanpicker_6// "timeSpanPickerRandomDelay"
0x7bbb7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bbbc  ldarg.0
0x7bbbd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRandomDelay
0x7bbc2  ldstr    aTimespanpicker_6// "timeSpanPickerRandomDelay"
0x7bbc7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bbcc  ldarg.0
0x7bbcd  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRandomDelay
0x7bbd2  ldstr    a000300// "00:03:00"
0x7bbd7  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x7bbdc  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x7bbe1  ldarg.0
0x7bbe2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bbe7  ldarg.0
0x7bbe8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionInterval
0x7bbed  ldc.i4.2
0x7bbee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bbf3  dup
0x7bbf4  ldarg.0
0x7bbf5  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionInterval
0x7bbfa  ldstr    aTimespanpicker_7// "timeSpanPickerRepetitionInterval"
0x7bbff  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bc04  ldarg.0
0x7bc05  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionInterval
0x7bc0a  ldstr    aTimespanpicker_7// "timeSpanPickerRepetitionInterval"
0x7bc0f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bc14  ldarg.0
0x7bc15  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionInterval
0x7bc1a  ldstr    a000300// "00:03:00"
0x7bc1f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x7bc24  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x7bc29  dup
0x7bc2a  ldarg.0
0x7bc2b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDuration
0x7bc30  ldstr    aTimespanpicker_8// "timeSpanPickerRepetitionDuration"
0x7bc35  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bc3a  ldarg.0
0x7bc3b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDuration
0x7bc40  ldstr    aTimespanpicker_8// "timeSpanPickerRepetitionDuration"
0x7bc45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bc4a  ldarg.0
0x7bc4b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerRepetitionDuration
0x7bc50  ldstr    a000300// "00:03:00"
0x7bc55  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x7bc5a  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x7bc5f  ldarg.0
0x7bc60  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bc65  ldarg.0
0x7bc66  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerExecutionLimit
0x7bc6b  ldc.i4.2
0x7bc6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bc71  dup
0x7bc72  ldarg.0
0x7bc73  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerExecutionLimit
0x7bc78  ldstr    aTimespanpicker_1// "timeSpanPickerExecutionLimit"
0x7bc7d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bc82  ldarg.0
0x7bc83  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerExecutionLimit
0x7bc88  ldstr    aTimespanpicker_1// "timeSpanPickerExecutionLimit"
0x7bc8d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bc92  ldarg.0
0x7bc93  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::timeSpanPickerExecutionLimit
0x7bc98  ldstr    a000300// "00:03:00"
0x7bc9d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x7bca2  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x7bca7  ldarg.0
0x7bca8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bcad  ldarg.0
0x7bcae  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxExecutionLimit
0x7bcb3  ldc.i4.4
0x7bcb4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bcb9  dup
0x7bcba  ldarg.0
0x7bcbb  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxExecutionLimit
0x7bcc0  ldstr    aCheckboxexecut_0// "checkBoxExecutionLimit"
0x7bcc5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bcca  ldarg.0
0x7bccb  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxExecutionLimit
0x7bcd0  ldstr    aCheckboxexecut_0// "checkBoxExecutionLimit"
0x7bcd5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bcda  ldarg.0
0x7bcdb  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxExecutionLimit
0x7bce0  ldarg.0
0x7bce1  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxExecutionLimit_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x7bce7  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7bcec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x7bcf1  ldarg.0
0x7bcf2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bcf7  ldarg.0
0x7bcf8  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxStopAtDurationEnd
0x7bcfd  ldc.i4.6
0x7bcfe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bd03  dup
0x7bd04  ldarg.0
0x7bd05  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxStopAtDurationEnd
0x7bd0a  ldstr    aCheckboxstopat// "checkBoxStopAtDurationEnd"
0x7bd0f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bd14  ldarg.0
0x7bd15  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxStopAtDurationEnd
0x7bd1a  ldstr    aCheckboxstopat// "checkBoxStopAtDurationEnd"
0x7bd1f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bd24  ldarg.0
0x7bd25  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bd2a  ldarg.0
0x7bd2b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::labelDurationOf
0x7bd30  ldc.i4.2
0x7bd31  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bd36  dup
0x7bd37  ldarg.0
0x7bd38  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::labelDurationOf
0x7bd3d  ldstr    aLabeldurationo// "labelDurationOf"
0x7bd42  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bd47  ldarg.0
0x7bd48  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::labelDurationOf
0x7bd4d  ldstr    aLabeldurationo// "labelDurationOf"
0x7bd52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bd57  ldarg.0
0x7bd58  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bd5d  ldarg.0
0x7bd5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxRepetitionInterval
0x7bd63  ldc.i4.3
0x7bd64  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bd69  dup
0x7bd6a  ldarg.0
0x7bd6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxRepetitionInterval
0x7bd70  ldstr    aCheckboxrepeti// "checkBoxRepetitionInterval"
0x7bd75  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bd7a  ldarg.0
0x7bd7b  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxRepetitionInterval
0x7bd80  ldstr    aCheckboxrepeti// "checkBoxRepetitionInterval"
0x7bd85  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bd8a  ldarg.0
0x7bd8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxRepetitionInterval
0x7bd90  ldarg.0
0x7bd91  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxRepetitionInterval_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x7bd97  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7bd9c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x7bda1  ldarg.0
0x7bda2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bda7  ldarg.0
0x7bda8  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxDelayTask
0x7bdad  ldc.i4.2
0x7bdae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bdb3  dup
0x7bdb4  ldarg.0
0x7bdb5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxDelayTask
0x7bdba  ldstr    aCheckboxdelayt// "checkBoxDelayTask"
0x7bdbf  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7bdc4  ldarg.0
0x7bdc5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxDelayTask
0x7bdca  ldstr    aCheckboxdelayt// "checkBoxDelayTask"
0x7bdcf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7bdd4  ldarg.0
0x7bdd5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxDelayTask
0x7bdda  ldarg.0
0x7bddb  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxDelayTask_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x7bde1  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7bde6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x7bdeb  ldarg.0
0x7bdec  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7bdf1  ldarg.0
0x7bdf2  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxActiveOn
0x7bdf7  ldc.i4.2
0x7bdf8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7bdfd  dup
0x7bdfe  ldarg.0
0x7bdff  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxActiveOn
0x7be04  ldstr    aCheckboxactive// "checkBoxActiveOn"
0x7be09  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7be0e  ldarg.0
0x7be0f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxActiveOn
0x7be14  ldstr    aCheckboxactive// "checkBoxActiveOn"
0x7be19  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7be1e  ldarg.0
0x7be1f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxActiveOn
0x7be24  ldarg.0
0x7be25  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::checkBoxActiveOn_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x7be2b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7be30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x7be35  dup
0x7be36  ldarg.0
0x7be37  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::dateTimePickerActiveOn
0x7be3c  ldstr    aDatetimepicker_1// "dateTimePickerActiveOn"
0x7be41  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7be46  ldarg.0
0x7be47  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::tableLayoutPanelSettings
0x7be4c  ldarg.0
0x7be4d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::dateTimePickerActiveOn
0x7be52  ldc.i4.4
0x7be53  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7be58  ldarg.0
0x7be59  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::dateTimePickerActiveOn
0x7be5e  ldstr    aDatetimepicker_1// "dateTimePickerActiveOn"
0x7be63  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7be68  ldarg.0
0x7be69  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::dateTimePickerActiveOn
0x7be6e  ldc.i4   0x7D6
0x7be73  ldc.i4.3
0x7be74  ldc.i4.s 0xB
0x7be76  ldc.i4.8
0x7be77  ldc.i4.s 0x23
0x7be79  ldc.i4.s 0xA
0x7be7b  ldc.i4   0x19D
0x7be80  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, int32)
0x7be85  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.FullDateTimePicker::set_Value(valuetype [mscorlib]System.DateTime value)
0x7be8a  ldarg.0
  ... truncated ...
```
