# Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::InitializeComponent

- ea: `0x6a010`
- end: `0x6a482`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::InitializeComponent`
- size: `1138`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x69a70`

## string_xrefs

- `0x6a23e`: `comboBoxAction`
- `0x6a24e`: `comboBoxAction`

## pseudocode

```c

```

## disassembly

```asm
0x6a010  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog
0x6a015  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6a01a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x6a01f  ldarg.0
0x6a020  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x6a025  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonCancel
0x6a02a  ldarg.0
0x6a02b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x6a030  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonOk
0x6a035  ldarg.0
0x6a036  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6a03b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelDescriptionActionSwitch
0x6a040  ldarg.0
0x6a041  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x6a046  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::groupBoxActionSettings
0x6a04b  ldarg.0
0x6a04c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x6a051  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x6a056  ldarg.0
0x6a057  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x6a05c  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a061  ldarg.0
0x6a062  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6a067  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelAction
0x6a06c  ldarg.0
0x6a06d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x6a072  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a077  ldarg.0
0x6a078  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x6a07d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelSeparator
0x6a082  ldarg.0
0x6a083  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x6a088  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanel1
0x6a08d  ldarg.0
0x6a08e  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::groupBoxActionSettings
0x6a093  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6a098  ldarg.0
0x6a099  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a09e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6a0a3  ldarg.0
0x6a0a4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanel1
0x6a0a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6a0ae  ldarg.0
0x6a0af  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x6a0b4  ldarg.0
0x6a0b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonCancel
0x6a0ba  ldc.i4.2
0x6a0bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6a0c0  dup
0x6a0c1  ldarg.0
0x6a0c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonCancel
0x6a0c7  ldstr    aButtoncancel// "buttonCancel"
0x6a0cc  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a0d1  ldarg.0
0x6a0d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonCancel
0x6a0d7  ldc.i4.s 0x4C
0x6a0d9  ldc.i4.s 0x17
0x6a0db  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x6a0e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x6a0e5  ldarg.0
0x6a0e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonCancel
0x6a0eb  ldstr    aButtoncancel// "buttonCancel"
0x6a0f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a0f5  ldarg.0
0x6a0f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonCancel
0x6a0fb  ldarg.0
0x6a0fc  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::OnCancel_Click(object sender, class [mscorlib]System.EventArgs e)
0x6a102  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6a107  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6a10c  dup
0x6a10d  ldarg.0
0x6a10e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonOk
0x6a113  ldstr    aButtonok_0// "buttonOk"
0x6a118  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a11d  ldarg.0
0x6a11e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonOk
0x6a123  ldc.i4.1
0x6a124  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x6a129  ldarg.0
0x6a12a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonOk
0x6a12f  ldc.i4.s 0x4C
0x6a131  ldc.i4.s 0x17
0x6a133  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x6a138  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x6a13d  ldarg.0
0x6a13e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonOk
0x6a143  ldstr    aButtonok_0// "buttonOk"
0x6a148  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a14d  ldarg.0
0x6a14e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonOk
0x6a153  ldarg.0
0x6a154  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::OkButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x6a15a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6a15f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x6a164  ldarg.0
0x6a165  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a16a  ldarg.0
0x6a16b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelDescriptionActionSwitch
0x6a170  ldc.i4.3
0x6a171  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6a176  dup
0x6a177  ldarg.0
0x6a178  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelDescriptionActionSwitch
0x6a17d  ldstr    aLabeldescripti_3// "labelDescriptionActionSwitch"
0x6a182  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a187  ldarg.0
0x6a188  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelDescriptionActionSwitch
0x6a18d  ldstr    aLabeldescripti_3// "labelDescriptionActionSwitch"
0x6a192  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a197  ldarg.0
0x6a198  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a19d  ldarg.0
0x6a19e  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::groupBoxActionSettings
0x6a1a3  ldc.i4.2
0x6a1a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6a1a9  ldarg.0
0x6a1aa  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::groupBoxActionSettings
0x6a1af  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6a1b4  ldarg.0
0x6a1b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x6a1ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6a1bf  dup
0x6a1c0  ldarg.0
0x6a1c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::groupBoxActionSettings
0x6a1c6  ldstr    aGroupboxaction// "groupBoxActionSettings"
0x6a1cb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a1d0  ldarg.0
0x6a1d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::groupBoxActionSettings
0x6a1d6  ldstr    aGroupboxaction// "groupBoxActionSettings"
0x6a1db  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a1e0  ldarg.0
0x6a1e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::groupBoxActionSettings
0x6a1e6  ldc.i4.0
0x6a1e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x6a1ec  dup
0x6a1ed  ldarg.0
0x6a1ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x6a1f3  ldstr    aPaneldynamicac// "panelDynamicAction"
0x6a1f8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a1fd  ldarg.0
0x6a1fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::panelDynamicAction
0x6a203  ldstr    aPaneldynamicac// "panelDynamicAction"
0x6a208  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a20d  ldarg.0
0x6a20e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a213  ldarg.0
0x6a214  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a219  ldc.i4.2
0x6a21a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6a21f  ldarg.0
0x6a220  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a225  ldc.i4.2
0x6a226  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x6a22b  ldarg.0
0x6a22c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a231  ldc.i4.1
0x6a232  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x6a237  dup
0x6a238  ldarg.0
0x6a239  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a23e  ldstr    aComboboxaction// "comboBoxAction"
0x6a243  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a248  ldarg.0
0x6a249  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a24e  ldstr    aComboboxaction// "comboBoxAction"
0x6a253  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a258  ldarg.0
0x6a259  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a25e  ldarg.0
0x6a25f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBox1_LostFocus(object sender, class [mscorlib]System.EventArgs e)
0x6a265  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6a26a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_LostFocus(class [mscorlib]System.EventHandler)
0x6a26f  ldarg.0
0x6a270  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a275  ldarg.0
0x6a276  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBox1_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x6a27c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x6a281  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x6a286  dup
0x6a287  ldarg.0
0x6a288  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelAction
0x6a28d  ldstr    aLabelaction// "labelAction"
0x6a292  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a297  ldarg.0
0x6a298  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelAction
0x6a29d  ldstr    aLabelaction// "labelAction"
0x6a2a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a2a7  dup
0x6a2a8  ldarg.0
0x6a2a9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a2ae  ldstr    aTablelayoutpan_9// "tableLayoutPanelActions"
0x6a2b3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a2b8  ldarg.0
0x6a2b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a2be  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6a2c3  ldarg.0
0x6a2c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelDescriptionActionSwitch
0x6a2c9  ldc.i4.0
0x6a2ca  ldc.i4.0
0x6a2cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6a2d0  ldarg.0
0x6a2d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a2d6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6a2db  ldarg.0
0x6a2dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::comboBoxAction
0x6a2e1  ldc.i4.1
0x6a2e2  ldc.i4.2
0x6a2e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6a2e8  ldarg.0
0x6a2e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a2ee  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6a2f3  ldarg.0
0x6a2f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelAction
0x6a2f9  ldc.i4.0
0x6a2fa  ldc.i4.2
0x6a2fb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6a300  ldarg.0
0x6a301  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a306  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6a30b  ldarg.0
0x6a30c  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::groupBoxActionSettings
0x6a311  ldc.i4.0
0x6a312  ldc.i4.3
0x6a313  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6a318  ldarg.0
0x6a319  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a31e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6a323  ldarg.0
0x6a324  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelSeparator
0x6a329  ldc.i4.0
0x6a32a  ldc.i4.1
0x6a32b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6a330  ldarg.0
0x6a331  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a336  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6a33b  ldarg.0
0x6a33c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanel1
0x6a341  ldc.i4.1
0x6a342  ldc.i4.4
0x6a343  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6a348  ldarg.0
0x6a349  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a34e  ldstr    aTablelayoutpan_9// "tableLayoutPanelActions"
0x6a353  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a358  dup
0x6a359  ldarg.0
0x6a35a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelSeparator
0x6a35f  ldstr    aLabelseparator// "labelSeparator"
0x6a364  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a369  ldarg.0
0x6a36a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelSeparator
0x6a36f  ldc.i4.2
0x6a370  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0x6a375  ldarg.0
0x6a376  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a37b  ldarg.0
0x6a37c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelSeparator
0x6a381  ldc.i4.4
0x6a382  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x6a387  ldarg.0
0x6a388  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::labelSeparator
0x6a38d  ldstr    aLabelseparator// "labelSeparator"
0x6a392  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a397  dup
0x6a398  ldarg.0
0x6a399  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanel1
0x6a39e  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x6a3a3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a3a8  ldarg.0
0x6a3a9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanel1
0x6a3ae  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6a3b3  ldarg.0
0x6a3b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonOk
0x6a3b9  ldc.i4.0
0x6a3ba  ldc.i4.0
0x6a3bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6a3c0  ldarg.0
0x6a3c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanel1
0x6a3c6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x6a3cb  ldarg.0
0x6a3cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::buttonCancel
0x6a3d1  ldc.i4.1
0x6a3d2  ldc.i4.0
0x6a3d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x6a3d8  ldarg.0
0x6a3d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanel1
0x6a3de  ldstr    aTablelayoutpan// "tableLayoutPanel1"
0x6a3e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x6a3e8  ldarg.0
0x6a3e9  ldstr    aThis// "$this"
0x6a3ee  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x6a3f3  ldarg.0
0x6a3f4  ldc.i4.2
0x6a3f5  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x6a3fa  ldarg.0
0x6a3fb  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x6a400  ldarg.0
0x6a401  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ActionSwitchDialog::tableLayoutPanelActions
0x6a406  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x6a40b  ldarg.0
  ... truncated ...
```
