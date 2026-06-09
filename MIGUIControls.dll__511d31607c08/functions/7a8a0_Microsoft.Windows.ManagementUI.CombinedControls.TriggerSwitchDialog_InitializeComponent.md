# Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::InitializeComponent

- ea: `0x7a8a0`
- end: `0x7ad07`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::InitializeComponent`
- size: `1127`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x79a50`

## callees

- `0x7ada0`
- `0x7aec0`

## string_xrefs

- `0x7aa06`: `comboBoxTask`
- `0x7aa16`: `comboBoxTask`
- `0x7aa3e`: `labelBeginTask`
- `0x7aa4e`: `labelBeginTask`

## pseudocode

```c

```

## disassembly

```asm
0x7a8a0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog
0x7a8a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7a8aa  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x7a8af  ldarg.0
0x7a8b0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x7a8b5  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonCancel
0x7a8ba  ldarg.0
0x7a8bb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x7a8c0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonOK
0x7a8c5  ldarg.0
0x7a8c6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x7a8cb  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x7a8d0  ldarg.0
0x7a8d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7a8d6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::labelBeginTask
0x7a8db  ldarg.0
0x7a8dc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x7a8e1  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxSettings
0x7a8e6  ldarg.0
0x7a8e7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.UserControl::.ctor()
0x7a8ec  stfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x7a8f1  ldarg.0
0x7a8f2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x7a8f7  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxAdvancedSettings
0x7a8fc  ldarg.0
0x7a8fd  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::.ctor()
0x7a902  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x7a907  ldarg.0
0x7a908  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x7a90d  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonTableLayoutPanel
0x7a912  ldarg.0
0x7a913  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x7a918  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7a91d  ldarg.0
0x7a91e  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxSettings
0x7a923  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7a928  ldarg.0
0x7a929  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxAdvancedSettings
0x7a92e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7a933  ldarg.0
0x7a934  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7a939  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7a93e  ldarg.0
0x7a93f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonTableLayoutPanel
0x7a944  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7a949  ldarg.0
0x7a94a  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7a94f  ldarg.0
0x7a950  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonCancel
0x7a955  ldc.i4.2
0x7a956  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x7a95b  dup
0x7a95c  ldarg.0
0x7a95d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonCancel
0x7a962  ldstr    aButtoncancel// "buttonCancel"
0x7a967  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7a96c  ldarg.0
0x7a96d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonCancel
0x7a972  ldstr    aButtoncancel// "buttonCancel"
0x7a977  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7a97c  ldarg.0
0x7a97d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonCancel
0x7a982  ldarg.0
0x7a983  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::OnCancel_Click(object sender, class [mscorlib]System.EventArgs e)
0x7a989  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7a98e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x7a993  ldarg.0
0x7a994  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonOK
0x7a999  ldc.i4.1
0x7a99a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x7a99f  dup
0x7a9a0  ldarg.0
0x7a9a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonOK
0x7a9a6  ldstr    aButtonok// "buttonOK"
0x7a9ab  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7a9b0  ldarg.0
0x7a9b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonOK
0x7a9b6  ldstr    aButtonok// "buttonOK"
0x7a9bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7a9c0  ldarg.0
0x7a9c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonOK
0x7a9c6  ldarg.0
0x7a9c7  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::OkButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x7a9cd  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7a9d2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x7a9d7  ldarg.0
0x7a9d8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x7a9dd  ldc.i4   0x9C
0x7a9e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownHeight(int32)
0x7a9e7  ldarg.0
0x7a9e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x7a9ed  ldc.i4.2
0x7a9ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x7a9f3  ldarg.0
0x7a9f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x7a9f9  ldc.i4.1
0x7a9fa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x7a9ff  dup
0x7aa00  ldarg.0
0x7aa01  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x7aa06  ldstr    aComboboxtask// "comboBoxTask"
0x7aa0b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7aa10  ldarg.0
0x7aa11  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x7aa16  ldstr    aComboboxtask// "comboBoxTask"
0x7aa1b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7aa20  ldarg.0
0x7aa21  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x7aa26  ldarg.0
0x7aa27  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBox1_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x7aa2d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7aa32  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x7aa37  dup
0x7aa38  ldarg.0
0x7aa39  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::labelBeginTask
0x7aa3e  ldstr    aLabelbegintask// "labelBeginTask"
0x7aa43  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7aa48  ldarg.0
0x7aa49  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::labelBeginTask
0x7aa4e  ldstr    aLabelbegintask// "labelBeginTask"
0x7aa53  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7aa58  ldarg.0
0x7aa59  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7aa5e  ldarg.0
0x7aa5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxSettings
0x7aa64  ldc.i4.4
0x7aa65  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7aa6a  ldarg.0
0x7aa6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxSettings
0x7aa70  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7aa75  ldarg.0
0x7aa76  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x7aa7b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7aa80  dup
0x7aa81  ldarg.0
0x7aa82  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxSettings
0x7aa87  ldstr    aGroupboxsettin// "groupBoxSettings"
0x7aa8c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7aa91  ldarg.0
0x7aa92  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxSettings
0x7aa97  ldstr    aGroupboxsettin// "groupBoxSettings"
0x7aa9c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7aaa1  ldarg.0
0x7aaa2  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxSettings
0x7aaa7  ldc.i4.0
0x7aaa8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x7aaad  dup
0x7aaae  ldarg.0
0x7aaaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x7aab4  ldstr    aPaneldynamictr// "panelDynamicTrigger"
0x7aab9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7aabe  ldarg.0
0x7aabf  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x7aac4  ldstr    aPaneldynamictr// "panelDynamicTrigger"
0x7aac9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7aace  ldarg.0
0x7aacf  ldfld    class [System.Windows.Forms]System.Windows.Forms.UserControl Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::panelDynamicTrigger
0x7aad4  ldc.i4.5
0x7aad5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x7aada  ldarg.0
0x7aadb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7aae0  ldarg.0
0x7aae1  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxAdvancedSettings
0x7aae6  ldc.i4.4
0x7aae7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7aaec  ldarg.0
0x7aaed  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxAdvancedSettings
0x7aaf2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7aaf7  ldarg.0
0x7aaf8  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x7aafd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7ab02  dup
0x7ab03  ldarg.0
0x7ab04  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxAdvancedSettings
0x7ab09  ldstr    aGroupboxadvanc// "groupBoxAdvancedSettings"
0x7ab0e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7ab13  ldarg.0
0x7ab14  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxAdvancedSettings
0x7ab19  ldstr    aGroupboxadvanc// "groupBoxAdvancedSettings"
0x7ab1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7ab23  ldarg.0
0x7ab24  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxAdvancedSettings
0x7ab29  ldc.i4.0
0x7ab2a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x7ab2f  dup
0x7ab30  ldarg.0
0x7ab31  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x7ab36  ldstr    aControltrigger_1// "controlTriggerSettings"
0x7ab3b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7ab40  ldarg.0
0x7ab41  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x7ab46  ldstr    aControltrigger_1// "controlTriggerSettings"
0x7ab4b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7ab50  ldarg.0
0x7ab51  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::controlTriggerSettings
0x7ab56  ldc.i4.0
0x7ab57  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlAdvancedTriggerSettings::set_SupportedDelayType(valuetype DelayTypeEnum value)
0x7ab5c  dup
0x7ab5d  ldarg.0
0x7ab5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonTableLayoutPanel
0x7ab63  ldstr    aButtontablelay// "buttonTableLayoutPanel"
0x7ab68  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7ab6d  ldarg.0
0x7ab6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonTableLayoutPanel
0x7ab73  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7ab78  ldarg.0
0x7ab79  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonOK
0x7ab7e  ldc.i4.0
0x7ab7f  ldc.i4.0
0x7ab80  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7ab85  ldarg.0
0x7ab86  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonTableLayoutPanel
0x7ab8b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7ab90  ldarg.0
0x7ab91  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonCancel
0x7ab96  ldc.i4.1
0x7ab97  ldc.i4.0
0x7ab98  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7ab9d  ldarg.0
0x7ab9e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonTableLayoutPanel
0x7aba3  ldstr    aButtontablelay// "buttonTableLayoutPanel"
0x7aba8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7abad  ldarg.0
0x7abae  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonTableLayoutPanel
0x7abb3  ldc.i4.5
0x7abb4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x7abb9  dup
0x7abba  ldarg.0
0x7abbb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7abc0  ldstr    aTablelayoutpan_20// "tableLayoutPanelTriggerSwitch"
0x7abc5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7abca  ldarg.0
0x7abcb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7abd0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7abd5  ldarg.0
0x7abd6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::labelBeginTask
0x7abdb  ldc.i4.0
0x7abdc  ldc.i4.0
0x7abdd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7abe2  ldarg.0
0x7abe3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7abe8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7abed  ldarg.0
0x7abee  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxAdvancedSettings
0x7abf3  ldc.i4.0
0x7abf4  ldc.i4.2
0x7abf5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7abfa  ldarg.0
0x7abfb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7ac00  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7ac05  ldarg.0
0x7ac06  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::comboBoxTask
0x7ac0b  ldc.i4.1
0x7ac0c  ldc.i4.0
0x7ac0d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7ac12  ldarg.0
0x7ac13  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7ac18  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7ac1d  ldarg.0
0x7ac1e  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::groupBoxSettings
0x7ac23  ldc.i4.0
0x7ac24  ldc.i4.1
0x7ac25  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7ac2a  ldarg.0
0x7ac2b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7ac30  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x7ac35  ldarg.0
0x7ac36  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::buttonTableLayoutPanel
0x7ac3b  ldc.i4.3
0x7ac3c  ldc.i4.3
0x7ac3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x7ac42  ldarg.0
0x7ac43  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7ac48  ldstr    aTablelayoutpan_20// "tableLayoutPanelTriggerSwitch"
0x7ac4d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7ac52  ldarg.0
0x7ac53  ldstr    aThis// "$this"
0x7ac58  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7ac5d  ldarg.0
0x7ac5e  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x7ac63  ldarg.0
0x7ac64  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.TriggerSwitchDialog::tableLayoutPanelTriggerSwitch
0x7ac69  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x7ac6e  ldarg.0
0x7ac6f  ldc.i4.3
0x7ac70  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_FormBorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FormBorderStyle)
0x7ac75  ldarg.0
0x7ac76  ldc.i4.0
0x7ac77  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MaximizeBox(bool)
0x7ac7c  ldarg.0
0x7ac7d  ldc.i4.0
0x7ac7e  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MinimizeBox(bool)
0x7ac83  ldarg.0
0x7ac84  ldstr    aTriggerswitchd// "TriggerSwitchDialog"
0x7ac89  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7ac8e  ldarg.0
0x7ac8f  ldc.i4.0
0x7ac90  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ShowInTaskbar(bool)
0x7ac95  ldarg.0
0x7ac96  ldc.i4.0
  ... truncated ...
```
