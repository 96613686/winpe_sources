# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::InitializeComponent

- ea: `0x70b00`
- end: `0x7122f`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::InitializeComponent`
- size: `1839`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x6ff50`

## callees

- `0x18ae0`
- `0x18b10`

## string_xrefs

- `0x70ce1`: `checkBoxComputerIdleFor`
- `0x70cf1`: `checkBoxComputerIdleFor`
- `0x70f9c`: `comboBoxRunOnlyIfNetworkAvailable`
- `0x70fd6`: `comboBoxRunOnlyIfNetworkAvailable`
- `0x71206`: `ControlTaskConditions`

## pseudocode

```c

```

## disassembly

```asm
0x70b00  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions
0x70b05  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x70b0a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x70b0f  ldarg.0
0x70b10  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x70b15  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::timeSpanPickerIdleDuration
0x70b1a  ldarg.0
0x70b1b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x70b20  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::timeSpanPickerIdleWaitTimeOut
0x70b25  ldarg.0
0x70b26  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x70b2b  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxIdleStopOnIdleEnd
0x70b30  ldarg.0
0x70b31  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x70b36  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelWaitIdleFor
0x70b3b  ldarg.0
0x70b3c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x70b41  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxComputerIdleFor
0x70b46  ldarg.0
0x70b47  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x70b4c  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStopIfGoingOnBatteries
0x70b51  ldarg.0
0x70b52  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x70b57  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStartIfNotGoingOnBatteries
0x70b5c  ldarg.0
0x70b5d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x70b62  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxRunOnlyIfNetworkAvailable
0x70b67  ldarg.0
0x70b68  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x70b6d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleConditions
0x70b72  ldarg.0
0x70b73  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x70b78  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleSeparator
0x70b7d  ldarg.0
0x70b7e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x70b83  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelConditionsDescription
0x70b88  ldarg.0
0x70b89  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x70b8e  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerConditions
0x70b93  ldarg.0
0x70b94  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x70b99  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerSeparator
0x70b9e  ldarg.0
0x70b9f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x70ba4  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelNetworkConditions
0x70ba9  ldarg.0
0x70baa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x70baf  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelNetworkSeparator
0x70bb4  ldarg.0
0x70bb5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x70bba  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxWakeToRun
0x70bbf  ldarg.0
0x70bc0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x70bc5  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::comboBoxRunOnlyIfNetworkAvailable
0x70bca  ldarg.0
0x70bcb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x70bd0  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70bd5  ldarg.0
0x70bd6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x70bdb  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxIdleRestartOnIdle
0x70be0  ldarg.0
0x70be1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70be6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x70beb  ldarg.0
0x70bec  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x70bf1  dup
0x70bf2  ldarg.0
0x70bf3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::timeSpanPickerIdleDuration
0x70bf8  ldstr    aTimespanpicker_3// "timeSpanPickerIdleDuration"
0x70bfd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70c02  ldarg.0
0x70c03  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::timeSpanPickerIdleDuration
0x70c08  ldstr    aTimespanpicker_3// "timeSpanPickerIdleDuration"
0x70c0d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70c12  ldarg.0
0x70c13  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::timeSpanPickerIdleDuration
0x70c18  ldstr    a10675199024805// "-10675199.02:48:05.4775808"
0x70c1d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x70c22  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x70c27  dup
0x70c28  ldarg.0
0x70c29  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::timeSpanPickerIdleWaitTimeOut
0x70c2e  ldstr    aTimespanpicker_4// "timeSpanPickerIdleWaitTimeOut"
0x70c33  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70c38  ldarg.0
0x70c39  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::timeSpanPickerIdleWaitTimeOut
0x70c3e  ldstr    aTimespanpicker_4// "timeSpanPickerIdleWaitTimeOut"
0x70c43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70c48  ldarg.0
0x70c49  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::timeSpanPickerIdleWaitTimeOut
0x70c4e  ldstr    a10675199024805// "-10675199.02:48:05.4775808"
0x70c53  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Parse(string)
0x70c58  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::set_Value(valuetype [mscorlib]System.TimeSpan value)
0x70c5d  ldarg.0
0x70c5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70c63  ldarg.0
0x70c64  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxIdleStopOnIdleEnd
0x70c69  ldc.i4.6
0x70c6a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70c6f  dup
0x70c70  ldarg.0
0x70c71  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxIdleStopOnIdleEnd
0x70c76  ldstr    aCheckboxidlest// "checkBoxIdleStopOnIdleEnd"
0x70c7b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70c80  ldarg.0
0x70c81  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxIdleStopOnIdleEnd
0x70c86  ldstr    aCheckboxidlest// "checkBoxIdleStopOnIdleEnd"
0x70c8b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70c90  ldarg.0
0x70c91  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxIdleStopOnIdleEnd
0x70c96  ldarg.0
0x70c97  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxIdleStopOnIdleEnd_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x70c9d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x70ca2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x70ca7  dup
0x70ca8  ldarg.0
0x70ca9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelWaitIdleFor
0x70cae  ldstr    aLabelwaitidlef// "labelWaitIdleFor"
0x70cb3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70cb8  ldarg.0
0x70cb9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelWaitIdleFor
0x70cbe  ldstr    aLabelwaitidlef// "labelWaitIdleFor"
0x70cc3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70cc8  ldarg.0
0x70cc9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70cce  ldarg.0
0x70ccf  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxComputerIdleFor
0x70cd4  ldc.i4.5
0x70cd5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70cda  dup
0x70cdb  ldarg.0
0x70cdc  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxComputerIdleFor
0x70ce1  ldstr    aCheckboxcomput// "checkBoxComputerIdleFor"
0x70ce6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70ceb  ldarg.0
0x70cec  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxComputerIdleFor
0x70cf1  ldstr    aCheckboxcomput// "checkBoxComputerIdleFor"
0x70cf6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70cfb  ldarg.0
0x70cfc  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxComputerIdleFor
0x70d01  ldarg.0
0x70d02  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkBoxComputerIdleFor_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x70d08  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x70d0d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x70d12  ldarg.0
0x70d13  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70d18  ldarg.0
0x70d19  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStopIfGoingOnBatteries
0x70d1e  ldc.i4.6
0x70d1f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70d24  dup
0x70d25  ldarg.0
0x70d26  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStopIfGoingOnBatteries
0x70d2b  ldstr    aCheckboxstopif// "checkboxStopIfGoingOnBatteries"
0x70d30  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70d35  ldarg.0
0x70d36  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStopIfGoingOnBatteries
0x70d3b  ldstr    aCheckboxstopif// "checkboxStopIfGoingOnBatteries"
0x70d40  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70d45  ldarg.0
0x70d46  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70d4b  ldarg.0
0x70d4c  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStartIfNotGoingOnBatteries
0x70d51  ldc.i4.7
0x70d52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70d57  dup
0x70d58  ldarg.0
0x70d59  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStartIfNotGoingOnBatteries
0x70d5e  ldstr    aCheckboxstarti// "checkboxStartIfNotGoingOnBatteries"
0x70d63  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70d68  ldarg.0
0x70d69  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStartIfNotGoingOnBatteries
0x70d6e  ldstr    aCheckboxstarti// "checkboxStartIfNotGoingOnBatteries"
0x70d73  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70d78  ldarg.0
0x70d79  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStartIfNotGoingOnBatteries
0x70d7e  ldarg.0
0x70d7f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxStartIfNotGoingOnBatteries_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x70d85  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x70d8a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x70d8f  ldarg.0
0x70d90  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70d95  ldarg.0
0x70d96  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxRunOnlyIfNetworkAvailable
0x70d9b  ldc.i4.7
0x70d9c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70da1  dup
0x70da2  ldarg.0
0x70da3  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxRunOnlyIfNetworkAvailable
0x70da8  ldstr    aCheckboxrunonl// "checkboxRunOnlyIfNetworkAvailable"
0x70dad  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70db2  ldarg.0
0x70db3  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxRunOnlyIfNetworkAvailable
0x70db8  ldstr    aCheckboxrunonl// "checkboxRunOnlyIfNetworkAvailable"
0x70dbd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70dc2  ldarg.0
0x70dc3  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxRunOnlyIfNetworkAvailable
0x70dc8  ldarg.0
0x70dc9  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::checkboxRunOnlyIfNetworkAvailable_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x70dcf  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x70dd4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x70dd9  ldarg.0
0x70dda  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70ddf  ldarg.0
0x70de0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleConditions
0x70de5  ldc.i4.3
0x70de6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70deb  dup
0x70dec  ldarg.0
0x70ded  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleConditions
0x70df2  ldstr    aLabelidlecondi// "labelIdleConditions"
0x70df7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70dfc  ldarg.0
0x70dfd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleConditions
0x70e02  ldstr    aLabelidlecondi// "labelIdleConditions"
0x70e07  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70e0c  dup
0x70e0d  ldarg.0
0x70e0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleSeparator
0x70e13  ldstr    aLabelidlesepar// "labelIdleSeparator"
0x70e18  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70e1d  ldarg.0
0x70e1e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleSeparator
0x70e23  ldc.i4.2
0x70e24  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x70e29  ldarg.0
0x70e2a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70e2f  ldarg.0
0x70e30  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleSeparator
0x70e35  ldc.i4.4
0x70e36  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70e3b  ldarg.0
0x70e3c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelIdleSeparator
0x70e41  ldstr    aLabelidlesepar// "labelIdleSeparator"
0x70e46  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70e4b  ldarg.0
0x70e4c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70e51  ldarg.0
0x70e52  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelConditionsDescription
0x70e57  ldc.i4.7
0x70e58  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70e5d  dup
0x70e5e  ldarg.0
0x70e5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelConditionsDescription
0x70e64  ldstr    aLabelcondition// "labelConditionsDescription"
0x70e69  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70e6e  ldarg.0
0x70e6f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelConditionsDescription
0x70e74  ldstr    aLabelcondition// "labelConditionsDescription"
0x70e79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70e7e  ldarg.0
0x70e7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70e84  ldarg.0
0x70e85  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerConditions
0x70e8a  ldc.i4.3
0x70e8b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70e90  dup
0x70e91  ldarg.0
0x70e92  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerConditions
0x70e97  ldstr    aLabelpowercond// "labelPowerConditions"
0x70e9c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70ea1  ldarg.0
0x70ea2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerConditions
0x70ea7  ldstr    aLabelpowercond// "labelPowerConditions"
0x70eac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70eb1  dup
0x70eb2  ldarg.0
0x70eb3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerSeparator
0x70eb8  ldstr    aLabelpowersepa// "labelPowerSeparator"
0x70ebd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70ec2  ldarg.0
0x70ec3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerSeparator
0x70ec8  ldc.i4.2
0x70ec9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x70ece  ldarg.0
0x70ecf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70ed4  ldarg.0
0x70ed5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerSeparator
0x70eda  ldc.i4.4
0x70edb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70ee0  ldarg.0
0x70ee1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelPowerSeparator
0x70ee6  ldstr    aLabelpowersepa// "labelPowerSeparator"
0x70eeb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70ef0  ldarg.0
0x70ef1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::tableLayoutPanelConditions
0x70ef6  ldarg.0
0x70ef7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelNetworkConditions
0x70efc  ldc.i4.4
0x70efd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x70f02  dup
0x70f03  ldarg.0
0x70f04  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelNetworkConditions
0x70f09  ldstr    aLabelnetworkco// "labelNetworkConditions"
0x70f0e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x70f13  ldarg.0
0x70f14  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditions::labelNetworkConditions
0x70f19  ldstr    aLabelnetworkco// "labelNetworkConditions"
0x70f1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x70f23  dup
  ... truncated ...
```
