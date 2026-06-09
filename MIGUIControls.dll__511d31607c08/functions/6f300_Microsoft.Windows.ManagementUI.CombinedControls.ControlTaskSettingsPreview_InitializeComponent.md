# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::InitializeComponent

- ea: `0x6f300`
- end: `0x6fa88`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::InitializeComponent`
- size: `1928`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ed60`

## callees

- `0x18ae0`
- `0x18b10`

## string_xrefs

- `0x6f618`: `labelTaskFails`
- `0x6f628`: `labelTaskFails`
- `0x6f4b4`: `timeSpanPickerDeleteExpiredTaskAfter`
- `0x6f4c4`: `timeSpanPickerDeleteExpiredTaskAfter`
- `0x6f53e`: `checkBoxDeleteExpired`
- `0x6f54e`: `checkBoxDeleteExpired`
- `0x6f639`: `checkBoxTaskFails`
- `0x6f649`: `checkBoxTaskFails`
- `0x6fa28`: `comboboxPolicy`
- `0x6fa38`: `comboboxPolicy`
- `0x6f571`: `labelDeleteTaskIf`
- `0x6f581`: `labelDeleteTaskIf`
- `0x6f747`: `labelReadOnlyDescription`
- `0x6f757`: `labelReadOnlyDescription`
- `0x6fa5f`: `ControlTaskSettingsPreview`

## pseudocode

```c

```

## disassembly

```asm
0x6f300  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview
0x6f305  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6f30a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x6f30f  ldarg.0
0x6f310  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x6f315  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerRestartInterval
0x6f31a  ldarg.0
0x6f31b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x6f320  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerExecutionLimit
0x6f325  ldarg.0
0x6f326  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x6f32b  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerDeleteExpiredTaskAfter
0x6f330  ldarg.0
0x6f331  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6f336  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxAllowHardTerminate
0x6f33b  ldarg.0
0x6f33c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f341  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelAllowHardTerminate
0x6f346  ldarg.0
0x6f347  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6f34c  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxDeleteExpired
0x6f351  ldarg.0
0x6f352  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f357  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelDeleteTaskIf
0x6f35c  ldarg.0
0x6f35d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6f362  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxExecutionTimeLimit
0x6f367  ldarg.0
0x6f368  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f36d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelExecutionTimeLimit
0x6f372  ldarg.0
0x6f373  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x6f378  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::textBoxRestartCount
0x6f37d  ldarg.0
0x6f37e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f383  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelTaskFails
0x6f388  ldarg.0
0x6f389  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6f38e  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxTaskFails
0x6f393  ldarg.0
0x6f394  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f399  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelStartWhenAvailable
0x6f39e  ldarg.0
0x6f39f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6f3a4  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxStartWhenAvailable
0x6f3a9  ldarg.0
0x6f3aa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f3af  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelDemandStart
0x6f3b4  ldarg.0
0x6f3b5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6f3ba  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxDemandStart
0x6f3bf  ldarg.0
0x6f3c0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f3c5  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelMultiplePolicy
0x6f3ca  ldarg.0
0x6f3cb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f3d0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelReadOnlyDescription
0x6f3d5  ldarg.0
0x6f3d6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f3db  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelPolicy
0x6f3e0  ldarg.0
0x6f3e1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f3e6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelTimesEvery
0x6f3eb  ldarg.0
0x6f3ec  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6f3f1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelTimes
0x6f3f6  ldarg.0
0x6f3f7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x6f3fc  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f401  ldarg.0
0x6f402  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x6f407  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::comboboxPolicy
0x6f40c  ldarg.0
0x6f40d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f412  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6f417  ldarg.0
0x6f418  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6f41d  dup
0x6f41e  ldarg.0
0x6f41f  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerRestartInterval
0x6f424  ldstr    aTimespanpicker_0// "timeSpanPickerRestartInterval"
0x6f429  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f42e  ldarg.0
0x6f42f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f434  ldarg.0
0x6f435  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerRestartInterval
0x6f43a  ldc.i4.2
0x6f43b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6f440  ldarg.0
0x6f441  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerRestartInterval
0x6f446  ldstr    aTimespanpicker_0// "timeSpanPickerRestartInterval"
0x6f44b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f450  ldarg.0
0x6f451  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerRestartInterval
0x6f456  ldstr    a10675199024805// "-10675199.02:48:05.4775808"
0x6f45b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x6f460  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x6f465  dup
0x6f466  ldarg.0
0x6f467  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerExecutionLimit
0x6f46c  ldstr    aTimespanpicker_1// "timeSpanPickerExecutionLimit"
0x6f471  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f476  ldarg.0
0x6f477  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f47c  ldarg.0
0x6f47d  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerExecutionLimit
0x6f482  ldc.i4.2
0x6f483  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6f488  ldarg.0
0x6f489  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerExecutionLimit
0x6f48e  ldstr    aTimespanpicker_1// "timeSpanPickerExecutionLimit"
0x6f493  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f498  ldarg.0
0x6f499  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerExecutionLimit
0x6f49e  ldstr    a10675199024805// "-10675199.02:48:05.4775808"
0x6f4a3  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x6f4a8  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x6f4ad  dup
0x6f4ae  ldarg.0
0x6f4af  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerDeleteExpiredTaskAfter
0x6f4b4  ldstr    aTimespanpicker_2// "timeSpanPickerDeleteExpiredTaskAfter"
0x6f4b9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f4be  ldarg.0
0x6f4bf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerDeleteExpiredTaskAfter
0x6f4c4  ldstr    aTimespanpicker_2// "timeSpanPickerDeleteExpiredTaskAfter"
0x6f4c9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f4ce  ldarg.0
0x6f4cf  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::timeSpanPickerDeleteExpiredTaskAfter
0x6f4d4  ldstr    a10675199024805// "-10675199.02:48:05.4775808"
0x6f4d9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x6f4de  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x6f4e3  dup
0x6f4e4  ldarg.0
0x6f4e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxAllowHardTerminate
0x6f4ea  ldstr    aCheckboxallowh// "checkboxAllowHardTerminate"
0x6f4ef  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f4f4  ldarg.0
0x6f4f5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxAllowHardTerminate
0x6f4fa  ldstr    aCheckboxallowh// "checkboxAllowHardTerminate"
0x6f4ff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f504  ldarg.0
0x6f505  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f50a  ldarg.0
0x6f50b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelAllowHardTerminate
0x6f510  ldc.i4.5
0x6f511  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6f516  dup
0x6f517  ldarg.0
0x6f518  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelAllowHardTerminate
0x6f51d  ldstr    aLabelallowhard// "labelAllowHardTerminate"
0x6f522  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f527  ldarg.0
0x6f528  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelAllowHardTerminate
0x6f52d  ldstr    aLabelallowhard// "labelAllowHardTerminate"
0x6f532  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f537  dup
0x6f538  ldarg.0
0x6f539  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxDeleteExpired
0x6f53e  ldstr    aCheckboxdelete// "checkBoxDeleteExpired"
0x6f543  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f548  ldarg.0
0x6f549  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxDeleteExpired
0x6f54e  ldstr    aCheckboxdelete// "checkBoxDeleteExpired"
0x6f553  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f558  ldarg.0
0x6f559  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f55e  ldarg.0
0x6f55f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelDeleteTaskIf
0x6f564  ldc.i4.3
0x6f565  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6f56a  dup
0x6f56b  ldarg.0
0x6f56c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelDeleteTaskIf
0x6f571  ldstr    aLabeldeletetas// "labelDeleteTaskIf"
0x6f576  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f57b  ldarg.0
0x6f57c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelDeleteTaskIf
0x6f581  ldstr    aLabeldeletetas// "labelDeleteTaskIf"
0x6f586  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f58b  dup
0x6f58c  ldarg.0
0x6f58d  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxExecutionTimeLimit
0x6f592  ldstr    aCheckboxexecut// "checkBoxExecutionTimeLimit"
0x6f597  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f59c  ldarg.0
0x6f59d  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxExecutionTimeLimit
0x6f5a2  ldstr    aCheckboxexecut// "checkBoxExecutionTimeLimit"
0x6f5a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f5ac  dup
0x6f5ad  ldarg.0
0x6f5ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelExecutionTimeLimit
0x6f5b3  ldstr    aLabelexecution// "labelExecutionTimeLimit"
0x6f5b8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f5bd  ldarg.0
0x6f5be  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelExecutionTimeLimit
0x6f5c3  ldstr    aLabelexecution// "labelExecutionTimeLimit"
0x6f5c8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f5cd  dup
0x6f5ce  ldarg.0
0x6f5cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::textBoxRestartCount
0x6f5d4  ldstr    aTextboxrestart// "textBoxRestartCount"
0x6f5d9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f5de  ldarg.0
0x6f5df  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::textBoxRestartCount
0x6f5e4  ldstr    aTextboxrestart// "textBoxRestartCount"
0x6f5e9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f5ee  ldarg.0
0x6f5ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::textBoxRestartCount
0x6f5f4  ldc.i4.1
0x6f5f5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x6f5fa  ldarg.0
0x6f5fb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::textBoxRestartCount
0x6f600  ldarg.0
0x6f601  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::textBoxRestartCount_KeyPress(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyPressEventArgs e)
0x6f607  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler::.ctor(object, native int)
0x6f60c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyPress(class [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler)
0x6f611  dup
0x6f612  ldarg.0
0x6f613  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelTaskFails
0x6f618  ldstr    aLabeltaskfails// "labelTaskFails"
0x6f61d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f622  ldarg.0
0x6f623  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelTaskFails
0x6f628  ldstr    aLabeltaskfails// "labelTaskFails"
0x6f62d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f632  dup
0x6f633  ldarg.0
0x6f634  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxTaskFails
0x6f639  ldstr    aCheckboxtaskfa// "checkBoxTaskFails"
0x6f63e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f643  ldarg.0
0x6f644  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkBoxTaskFails
0x6f649  ldstr    aCheckboxtaskfa// "checkBoxTaskFails"
0x6f64e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f653  ldarg.0
0x6f654  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f659  ldarg.0
0x6f65a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelStartWhenAvailable
0x6f65f  ldc.i4.5
0x6f660  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6f665  dup
0x6f666  ldarg.0
0x6f667  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelStartWhenAvailable
0x6f66c  ldstr    aLabelstartwhen// "labelStartWhenAvailable"
0x6f671  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f676  ldarg.0
0x6f677  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelStartWhenAvailable
0x6f67c  ldstr    aLabelstartwhen// "labelStartWhenAvailable"
0x6f681  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f686  dup
0x6f687  ldarg.0
0x6f688  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxStartWhenAvailable
0x6f68d  ldstr    aCheckboxstartw// "checkboxStartWhenAvailable"
0x6f692  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f697  ldarg.0
0x6f698  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxStartWhenAvailable
0x6f69d  ldstr    aCheckboxstartw// "checkboxStartWhenAvailable"
0x6f6a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f6a7  ldarg.0
0x6f6a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f6ad  ldarg.0
0x6f6ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelDemandStart
0x6f6b3  ldc.i4.5
0x6f6b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6f6b9  dup
0x6f6ba  ldarg.0
0x6f6bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelDemandStart
0x6f6c0  ldstr    aLabeldemandsta// "labelDemandStart"
0x6f6c5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f6ca  ldarg.0
0x6f6cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelDemandStart
0x6f6d0  ldstr    aLabeldemandsta// "labelDemandStart"
0x6f6d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f6da  dup
0x6f6db  ldarg.0
0x6f6dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxDemandStart
0x6f6e1  ldstr    aCheckboxdemand// "checkboxDemandStart"
0x6f6e6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f6eb  ldarg.0
0x6f6ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::checkboxDemandStart
0x6f6f1  ldstr    aCheckboxdemand// "checkboxDemandStart"
0x6f6f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f6fb  ldarg.0
0x6f6fc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f701  ldarg.0
0x6f702  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelMultiplePolicy
0x6f707  ldc.i4.6
0x6f708  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6f70d  dup
0x6f70e  ldarg.0
0x6f70f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelMultiplePolicy
0x6f714  ldstr    aLabelmultiplep// "labelMultiplePolicy"
0x6f719  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6f71e  ldarg.0
0x6f71f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::labelMultiplePolicy
0x6f724  ldstr    aLabelmultiplep// "labelMultiplePolicy"
0x6f729  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6f72e  ldarg.0
0x6f72f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettingsPreview::tableLayoutPanelSettings
0x6f734  ldarg.0
  ... truncated ...
```
