# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::InitializeComponent

- ea: `0x71930`
- end: `0x721c7`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::InitializeComponent`
- size: `2199`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x712a0`

## callees

- `0x18b10`

## string_xrefs

- `0x71b92`: `checkBoxComputerIdleFor`
- `0x71ba2`: `checkBoxComputerIdleFor`
- `0x71e8c`: `comboBoxRunOnlyIfNetworkAvailable`
- `0x71ed6`: `comboBoxRunOnlyIfNetworkAvailable`
- `0x71b71`: `labelComputerIdleFor`
- `0x71b81`: `labelComputerIdleFor`
- `0x71d33`: `labelConditionsReadOnlyDescription`
- `0x71d43`: `labelConditionsReadOnlyDescription`
- `0x7219e`: `ControlTaskConditionsPreview`

## pseudocode

```c

```

## disassembly

```asm
0x71930  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview
0x71935  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7193a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x7193f  ldarg.0
0x71940  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x71945  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::timeSpanPickerIdleDuration
0x7194a  ldarg.0
0x7194b  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker::.ctor()
0x71950  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::timeSpanPickerIdleWaitTimeOut
0x71955  ldarg.0
0x71956  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7195b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleStopOnIdleEnd
0x71960  ldarg.0
0x71961  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x71966  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkBoxIdleStopOnIdleEnd
0x7196b  ldarg.0
0x7196c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x71971  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleRestartOnIdle
0x71976  ldarg.0
0x71977  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7197c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelWaitIdleFor
0x71981  ldarg.0
0x71982  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x71987  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelComputerIdleFor
0x7198c  ldarg.0
0x7198d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x71992  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkBoxComputerIdleFor
0x71997  ldarg.0
0x71998  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7199d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelStopIfGoingOnBatteries
0x719a2  ldarg.0
0x719a3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x719a8  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxStopIfGoingOnBatteries
0x719ad  ldarg.0
0x719ae  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x719b3  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labeStartIfNotGoingOnBatteries
0x719b8  ldarg.0
0x719b9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x719be  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxStartIfNotGoingOnBatteries
0x719c3  ldarg.0
0x719c4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x719c9  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labeRunOnlyIfNetworkAvailable
0x719ce  ldarg.0
0x719cf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x719d4  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxRunOnlyIfNetworkAvailable
0x719d9  ldarg.0
0x719da  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x719df  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleConditions
0x719e4  ldarg.0
0x719e5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x719ea  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleSeparator
0x719ef  ldarg.0
0x719f0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x719f5  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelConditionsReadOnlyDescription
0x719fa  ldarg.0
0x719fb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x71a00  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelPowerConditions
0x71a05  ldarg.0
0x71a06  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x71a0b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelPowerSeparator
0x71a10  ldarg.0
0x71a11  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x71a16  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelNetworkConditions
0x71a1b  ldarg.0
0x71a1c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x71a21  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelNetworkSeparator
0x71a26  ldarg.0
0x71a27  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x71a2c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelWakeToRun
0x71a31  ldarg.0
0x71a32  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x71a37  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkBoxWakeToRun
0x71a3c  ldarg.0
0x71a3d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x71a42  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::comboBoxRunOnlyIfNetworkAvailable
0x71a47  ldarg.0
0x71a48  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x71a4d  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71a52  ldarg.0
0x71a53  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x71a58  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkBoxIdleRestartOnIdle
0x71a5d  ldarg.0
0x71a5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71a63  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x71a68  ldarg.0
0x71a69  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x71a6e  dup
0x71a6f  ldarg.0
0x71a70  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::timeSpanPickerIdleDuration
0x71a75  ldstr    aTimespanpicker_3// "timeSpanPickerIdleDuration"
0x71a7a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71a7f  ldarg.0
0x71a80  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::timeSpanPickerIdleDuration
0x71a85  ldstr    aTimespanpicker_3// "timeSpanPickerIdleDuration"
0x71a8a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71a8f  dup
0x71a90  ldarg.0
0x71a91  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::timeSpanPickerIdleWaitTimeOut
0x71a96  ldstr    aTimespanpicker_4// "timeSpanPickerIdleWaitTimeOut"
0x71a9b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71aa0  ldarg.0
0x71aa1  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TimeSpanPicker Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::timeSpanPickerIdleWaitTimeOut
0x71aa6  ldstr    aTimespanpicker_4// "timeSpanPickerIdleWaitTimeOut"
0x71aab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71ab0  ldarg.0
0x71ab1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71ab6  ldarg.0
0x71ab7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleStopOnIdleEnd
0x71abc  ldc.i4.3
0x71abd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71ac2  dup
0x71ac3  ldarg.0
0x71ac4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleStopOnIdleEnd
0x71ac9  ldstr    aLabelidlestopo// "labelIdleStopOnIdleEnd"
0x71ace  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71ad3  ldarg.0
0x71ad4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleStopOnIdleEnd
0x71ad9  ldstr    aLabelidlestopo// "labelIdleStopOnIdleEnd"
0x71ade  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71ae3  dup
0x71ae4  ldarg.0
0x71ae5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkBoxIdleStopOnIdleEnd
0x71aea  ldstr    aCheckboxidlest// "checkBoxIdleStopOnIdleEnd"
0x71aef  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71af4  ldarg.0
0x71af5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkBoxIdleStopOnIdleEnd
0x71afa  ldstr    aCheckboxidlest// "checkBoxIdleStopOnIdleEnd"
0x71aff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71b04  ldarg.0
0x71b05  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71b0a  ldarg.0
0x71b0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleRestartOnIdle
0x71b10  ldc.i4.3
0x71b11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71b16  dup
0x71b17  ldarg.0
0x71b18  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleRestartOnIdle
0x71b1d  ldstr    aLabelidleresta// "labelIdleRestartOnIdle"
0x71b22  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71b27  ldarg.0
0x71b28  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleRestartOnIdle
0x71b2d  ldstr    aLabelidleresta// "labelIdleRestartOnIdle"
0x71b32  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71b37  dup
0x71b38  ldarg.0
0x71b39  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelWaitIdleFor
0x71b3e  ldstr    aLabelwaitidlef// "labelWaitIdleFor"
0x71b43  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71b48  ldarg.0
0x71b49  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelWaitIdleFor
0x71b4e  ldstr    aLabelwaitidlef// "labelWaitIdleFor"
0x71b53  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71b58  ldarg.0
0x71b59  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71b5e  ldarg.0
0x71b5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelComputerIdleFor
0x71b64  ldc.i4.4
0x71b65  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71b6a  dup
0x71b6b  ldarg.0
0x71b6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelComputerIdleFor
0x71b71  ldstr    aLabelcomputeri// "labelComputerIdleFor"
0x71b76  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71b7b  ldarg.0
0x71b7c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelComputerIdleFor
0x71b81  ldstr    aLabelcomputeri// "labelComputerIdleFor"
0x71b86  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71b8b  dup
0x71b8c  ldarg.0
0x71b8d  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkBoxComputerIdleFor
0x71b92  ldstr    aCheckboxcomput// "checkBoxComputerIdleFor"
0x71b97  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71b9c  ldarg.0
0x71b9d  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkBoxComputerIdleFor
0x71ba2  ldstr    aCheckboxcomput// "checkBoxComputerIdleFor"
0x71ba7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71bac  ldarg.0
0x71bad  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71bb2  ldarg.0
0x71bb3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelStopIfGoingOnBatteries
0x71bb8  ldc.i4.4
0x71bb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71bbe  dup
0x71bbf  ldarg.0
0x71bc0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelStopIfGoingOnBatteries
0x71bc5  ldstr    aLabelstopifgoi// "labelStopIfGoingOnBatteries"
0x71bca  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71bcf  ldarg.0
0x71bd0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelStopIfGoingOnBatteries
0x71bd5  ldstr    aLabelstopifgoi// "labelStopIfGoingOnBatteries"
0x71bda  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71bdf  dup
0x71be0  ldarg.0
0x71be1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxStopIfGoingOnBatteries
0x71be6  ldstr    aCheckboxstopif// "checkboxStopIfGoingOnBatteries"
0x71beb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71bf0  ldarg.0
0x71bf1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxStopIfGoingOnBatteries
0x71bf6  ldstr    aCheckboxstopif// "checkboxStopIfGoingOnBatteries"
0x71bfb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71c00  ldarg.0
0x71c01  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71c06  ldarg.0
0x71c07  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labeStartIfNotGoingOnBatteries
0x71c0c  ldc.i4.5
0x71c0d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71c12  dup
0x71c13  ldarg.0
0x71c14  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labeStartIfNotGoingOnBatteries
0x71c19  ldstr    aLabestartifnot// "labeStartIfNotGoingOnBatteries"
0x71c1e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71c23  ldarg.0
0x71c24  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labeStartIfNotGoingOnBatteries
0x71c29  ldstr    aLabestartifnot// "labeStartIfNotGoingOnBatteries"
0x71c2e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71c33  dup
0x71c34  ldarg.0
0x71c35  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxStartIfNotGoingOnBatteries
0x71c3a  ldstr    aCheckboxstarti// "checkboxStartIfNotGoingOnBatteries"
0x71c3f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71c44  ldarg.0
0x71c45  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxStartIfNotGoingOnBatteries
0x71c4a  ldstr    aCheckboxstarti// "checkboxStartIfNotGoingOnBatteries"
0x71c4f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71c54  ldarg.0
0x71c55  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71c5a  ldarg.0
0x71c5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labeRunOnlyIfNetworkAvailable
0x71c60  ldc.i4.5
0x71c61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71c66  dup
0x71c67  ldarg.0
0x71c68  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labeRunOnlyIfNetworkAvailable
0x71c6d  ldstr    aLaberunonlyifn// "labeRunOnlyIfNetworkAvailable"
0x71c72  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71c77  ldarg.0
0x71c78  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labeRunOnlyIfNetworkAvailable
0x71c7d  ldstr    aLaberunonlyifn// "labeRunOnlyIfNetworkAvailable"
0x71c82  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71c87  dup
0x71c88  ldarg.0
0x71c89  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxRunOnlyIfNetworkAvailable
0x71c8e  ldstr    aCheckboxrunonl// "checkboxRunOnlyIfNetworkAvailable"
0x71c93  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71c98  ldarg.0
0x71c99  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::checkboxRunOnlyIfNetworkAvailable
0x71c9e  ldstr    aCheckboxrunonl// "checkboxRunOnlyIfNetworkAvailable"
0x71ca3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71ca8  ldarg.0
0x71ca9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71cae  ldarg.0
0x71caf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleConditions
0x71cb4  ldc.i4.3
0x71cb5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71cba  dup
0x71cbb  ldarg.0
0x71cbc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleConditions
0x71cc1  ldstr    aLabelidlecondi// "labelIdleConditions"
0x71cc6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71ccb  ldarg.0
0x71ccc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleConditions
0x71cd1  ldstr    aLabelidlecondi// "labelIdleConditions"
0x71cd6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71cdb  dup
0x71cdc  ldarg.0
0x71cdd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleSeparator
0x71ce2  ldstr    aLabelidlesepar// "labelIdleSeparator"
0x71ce7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71cec  ldarg.0
0x71ced  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleSeparator
0x71cf2  ldc.i4.2
0x71cf3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x71cf8  ldarg.0
0x71cf9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71cfe  ldarg.0
0x71cff  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleSeparator
0x71d04  ldc.i4.4
0x71d05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71d0a  ldarg.0
0x71d0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelIdleSeparator
0x71d10  ldstr    aLabelidlesepar// "labelIdleSeparator"
0x71d15  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71d1a  ldarg.0
0x71d1b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71d20  ldarg.0
0x71d21  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelConditionsReadOnlyDescription
0x71d26  ldc.i4.7
0x71d27  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x71d2c  dup
0x71d2d  ldarg.0
0x71d2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelConditionsReadOnlyDescription
0x71d33  ldstr    aLabelcondition_0// "labelConditionsReadOnlyDescription"
0x71d38  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x71d3d  ldarg.0
0x71d3e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::labelConditionsReadOnlyDescription
0x71d43  ldstr    aLabelcondition_0// "labelConditionsReadOnlyDescription"
0x71d48  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x71d4d  ldarg.0
0x71d4e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskConditionsPreview::tableLayoutPanelConditions
0x71d53  ldarg.0
  ... truncated ...
```
