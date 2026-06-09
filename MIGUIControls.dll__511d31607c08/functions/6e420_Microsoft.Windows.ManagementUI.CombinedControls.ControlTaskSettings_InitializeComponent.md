# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::InitializeComponent

- ea: `0x6e420`
- end: `0x6ecb6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::InitializeComponent`
- size: `2198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6db60`

## callees

- `0x18ae0`
- `0x18b10`

## string_xrefs

- `0x6e5df`: `labelDeleteExpired`
- `0x6e601`: `labelDeleteExpired`
- `0x6e666`: `labelTaskFails`
- `0x6e676`: `labelTaskFails`
- `0x6e6db`: `timeSpanPickerDeleteExpiredTaskAfter`
- `0x6e6eb`: `timeSpanPickerDeleteExpiredTaskAfter`
- `0x6e748`: `checkBoxDeleteExpired`
- `0x6e758`: `checkBoxDeleteExpired`
- `0x6e81c`: `checkBoxTaskFails`
- `0x6e82c`: `checkBoxTaskFails`
- `0x6ec29`: `comboboxPolicy`
- `0x6ec39`: `comboboxPolicy`
- `0x6ec8d`: `ControlTaskSettings`

## pseudocode

```c

```

## disassembly

```asm
0x6e420  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings
0x6e425  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6e42a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x6e42f  ldarg.0
0x6e430  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x6e435  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerRestartInterval
0x6e43a  ldarg.0
0x6e43b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x6e440  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerExecutionLimit
0x6e445  ldarg.0
0x6e446  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x6e44b  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerDeleteExpiredTaskAfter
0x6e450  ldarg.0
0x6e451  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6e456  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkboxAllowHardTerminate
0x6e45b  ldarg.0
0x6e45c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6e461  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxDeleteExpired
0x6e466  ldarg.0
0x6e467  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6e46c  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxExecutionTimeLimit
0x6e471  ldarg.0
0x6e472  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x6e477  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::textBoxRestartCount
0x6e47c  ldarg.0
0x6e47d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6e482  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxTaskFails
0x6e487  ldarg.0
0x6e488  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6e48d  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkboxStartWhenAvailable
0x6e492  ldarg.0
0x6e493  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x6e498  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkboxDemandStart
0x6e49d  ldarg.0
0x6e49e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e4a3  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelMultiplePolicy
0x6e4a8  ldarg.0
0x6e4a9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e4ae  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDescription
0x6e4b3  ldarg.0
0x6e4b4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e4b9  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelTimes
0x6e4be  ldarg.0
0x6e4bf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x6e4c4  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::tableLayoutPanelSettings
0x6e4c9  ldarg.0
0x6e4ca  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e4cf  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelPermission
0x6e4d4  ldarg.0
0x6e4d5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e4da  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelTimesEvery
0x6e4df  ldarg.0
0x6e4e0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x6e4e5  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::comboboxPolicy
0x6e4ea  ldarg.0
0x6e4eb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x6e4f0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::buttonPermission
0x6e4f5  ldarg.0
0x6e4f6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e4fb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDeleteExpired
0x6e500  ldarg.0
0x6e501  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e506  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDemandStart
0x6e50b  ldarg.0
0x6e50c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e511  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelStartWhenAvailable
0x6e516  ldarg.0
0x6e517  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e51c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelTaskFails
0x6e521  ldarg.0
0x6e522  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e527  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelExecutionTimeLimit
0x6e52c  ldarg.0
0x6e52d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6e532  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelAllowHardTerminate
0x6e537  ldarg.0
0x6e538  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::tableLayoutPanelSettings
0x6e53d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6e542  ldarg.0
0x6e543  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6e548  dup
0x6e549  ldarg.0
0x6e54a  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerRestartInterval
0x6e54f  ldstr    aTimespanpicker_0// "timeSpanPickerRestartInterval"
0x6e554  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e559  ldarg.0
0x6e55a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::tableLayoutPanelSettings
0x6e55f  ldarg.0
0x6e560  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerRestartInterval
0x6e565  ldc.i4.2
0x6e566  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6e56b  ldarg.0
0x6e56c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerRestartInterval
0x6e571  ldstr    aTimespanpicker_0// "timeSpanPickerRestartInterval"
0x6e576  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e57b  ldarg.0
0x6e57c  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerRestartInterval
0x6e581  ldstr    a000300// "00:03:00"
0x6e586  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x6e58b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x6e590  dup
0x6e591  ldarg.0
0x6e592  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerExecutionLimit
0x6e597  ldstr    aTimespanpicker_1// "timeSpanPickerExecutionLimit"
0x6e59c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e5a1  ldarg.0
0x6e5a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::tableLayoutPanelSettings
0x6e5a7  ldarg.0
0x6e5a8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerExecutionLimit
0x6e5ad  ldc.i4.2
0x6e5ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6e5b3  ldarg.0
0x6e5b4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerExecutionLimit
0x6e5b9  ldstr    aTimespanpicker_1// "timeSpanPickerExecutionLimit"
0x6e5be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e5c3  ldarg.0
0x6e5c4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerExecutionLimit
0x6e5c9  ldstr    a000300// "00:03:00"
0x6e5ce  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x6e5d3  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x6e5d8  dup
0x6e5d9  ldarg.0
0x6e5da  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDeleteExpired
0x6e5df  ldstr    aLabeldeleteexp// "labelDeleteExpired"
0x6e5e4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e5e9  ldarg.0
0x6e5ea  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::tableLayoutPanelSettings
0x6e5ef  ldarg.0
0x6e5f0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDeleteExpired
0x6e5f5  ldc.i4.3
0x6e5f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6e5fb  ldarg.0
0x6e5fc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDeleteExpired
0x6e601  ldstr    aLabeldeleteexp// "labelDeleteExpired"
0x6e606  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e60b  dup
0x6e60c  ldarg.0
0x6e60d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDemandStart
0x6e612  ldstr    aLabeldemandsta// "labelDemandStart"
0x6e617  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e61c  ldarg.0
0x6e61d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDemandStart
0x6e622  ldstr    aLabeldemandsta// "labelDemandStart"
0x6e627  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e62c  dup
0x6e62d  ldarg.0
0x6e62e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelStartWhenAvailable
0x6e633  ldstr    aLabelstartwhen// "labelStartWhenAvailable"
0x6e638  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e63d  ldarg.0
0x6e63e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::tableLayoutPanelSettings
0x6e643  ldarg.0
0x6e644  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelStartWhenAvailable
0x6e649  ldc.i4.4
0x6e64a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6e64f  ldarg.0
0x6e650  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelStartWhenAvailable
0x6e655  ldstr    aLabelstartwhen// "labelStartWhenAvailable"
0x6e65a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e65f  dup
0x6e660  ldarg.0
0x6e661  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelTaskFails
0x6e666  ldstr    aLabeltaskfails// "labelTaskFails"
0x6e66b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e670  ldarg.0
0x6e671  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelTaskFails
0x6e676  ldstr    aLabeltaskfails// "labelTaskFails"
0x6e67b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e680  dup
0x6e681  ldarg.0
0x6e682  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelExecutionTimeLimit
0x6e687  ldstr    aLabelexecution// "labelExecutionTimeLimit"
0x6e68c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e691  ldarg.0
0x6e692  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelExecutionTimeLimit
0x6e697  ldstr    aLabelexecution// "labelExecutionTimeLimit"
0x6e69c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e6a1  dup
0x6e6a2  ldarg.0
0x6e6a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelAllowHardTerminate
0x6e6a8  ldstr    aLabelallowhard// "labelAllowHardTerminate"
0x6e6ad  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e6b2  ldarg.0
0x6e6b3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::tableLayoutPanelSettings
0x6e6b8  ldarg.0
0x6e6b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelAllowHardTerminate
0x6e6be  ldc.i4.4
0x6e6bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6e6c4  ldarg.0
0x6e6c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelAllowHardTerminate
0x6e6ca  ldstr    aLabelallowhard// "labelAllowHardTerminate"
0x6e6cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e6d4  dup
0x6e6d5  ldarg.0
0x6e6d6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerDeleteExpiredTaskAfter
0x6e6db  ldstr    aTimespanpicker_2// "timeSpanPickerDeleteExpiredTaskAfter"
0x6e6e0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e6e5  ldarg.0
0x6e6e6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerDeleteExpiredTaskAfter
0x6e6eb  ldstr    aTimespanpicker_2// "timeSpanPickerDeleteExpiredTaskAfter"
0x6e6f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e6f5  ldarg.0
0x6e6f6  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::timeSpanPickerDeleteExpiredTaskAfter
0x6e6fb  ldstr    a000300// "00:03:00"
0x6e700  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x6e705  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x6e70a  dup
0x6e70b  ldarg.0
0x6e70c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkboxAllowHardTerminate
0x6e711  ldstr    aCheckboxallowh// "checkboxAllowHardTerminate"
0x6e716  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e71b  ldarg.0
0x6e71c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkboxAllowHardTerminate
0x6e721  ldstr    aCheckboxallowh// "checkboxAllowHardTerminate"
0x6e726  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e72b  ldarg.0
0x6e72c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkboxAllowHardTerminate
0x6e731  ldarg.0
0x6e732  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelAllowHardTerminate
0x6e737  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x6e73c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x6e741  dup
0x6e742  ldarg.0
0x6e743  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxDeleteExpired
0x6e748  ldstr    aCheckboxdelete// "checkBoxDeleteExpired"
0x6e74d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e752  ldarg.0
0x6e753  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxDeleteExpired
0x6e758  ldstr    aCheckboxdelete// "checkBoxDeleteExpired"
0x6e75d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e762  ldarg.0
0x6e763  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxDeleteExpired
0x6e768  ldarg.0
0x6e769  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelDeleteExpired
0x6e76e  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x6e773  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x6e778  ldarg.0
0x6e779  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxDeleteExpired
0x6e77e  ldarg.0
0x6e77f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxDeleteExpired_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x6e785  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6e78a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x6e78f  dup
0x6e790  ldarg.0
0x6e791  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxExecutionTimeLimit
0x6e796  ldstr    aCheckboxexecut// "checkBoxExecutionTimeLimit"
0x6e79b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e7a0  ldarg.0
0x6e7a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxExecutionTimeLimit
0x6e7a6  ldstr    aCheckboxexecut// "checkBoxExecutionTimeLimit"
0x6e7ab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e7b0  ldarg.0
0x6e7b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxExecutionTimeLimit
0x6e7b6  ldarg.0
0x6e7b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelExecutionTimeLimit
0x6e7bc  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x6e7c1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x6e7c6  ldarg.0
0x6e7c7  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxExecutionTimeLimit
0x6e7cc  ldarg.0
0x6e7cd  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxExecutionTimeLimit_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x6e7d3  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6e7d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x6e7dd  dup
0x6e7de  ldarg.0
0x6e7df  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::textBoxRestartCount
0x6e7e4  ldstr    aTextboxrestart// "textBoxRestartCount"
0x6e7e9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e7ee  ldarg.0
0x6e7ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::textBoxRestartCount
0x6e7f4  ldstr    aTextboxrestart// "textBoxRestartCount"
0x6e7f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e7fe  ldarg.0
0x6e7ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::textBoxRestartCount
0x6e804  ldarg.0
0x6e805  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::textBoxRestartCount_KeyPress(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyPressEventArgs e)
0x6e80b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler::.ctor(object, native int)
0x6e810  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyPress(class [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler)
0x6e815  dup
0x6e816  ldarg.0
0x6e817  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxTaskFails
0x6e81c  ldstr    aCheckboxtaskfa// "checkBoxTaskFails"
0x6e821  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6e826  ldarg.0
0x6e827  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxTaskFails
0x6e82c  ldstr    aCheckboxtaskfa// "checkBoxTaskFails"
0x6e831  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6e836  ldarg.0
0x6e837  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxTaskFails
0x6e83c  ldarg.0
0x6e83d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::labelTaskFails
0x6e842  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x6e847  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x6e84c  ldarg.0
0x6e84d  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxTaskFails
0x6e852  ldarg.0
0x6e853  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskSettings::checkBoxTaskFails_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x6e859  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6e85e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x6e863  dup
  ... truncated ...
```
