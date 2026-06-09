# Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::InitializeComponent

- ea: `0x901b0`
- end: `0x90afe`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::InitializeComponent`
- size: `2382`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8e570`

## callees

- `0x1efc0`
- `0x8e440`

## string_xrefs

- `0x9049d`: `labelSecurity`
- `0x904ad`: `labelSecurity`
- `0x90437`: `copyExistingViewToolStripMenuItem`
- `0x90448`: `copyExistingViewToolStripMenuItem`
- `0x904df`: `filterConfiguredLabel`
- `0x904ef`: `filterConfiguredLabel`
- `0x90500`: `labelConfigureFilter`
- `0x90510`: `labelConfigureFilter`
- `0x905e2`: `logComboBox`
- `0x905f2`: `logComboBox`
- `0x90773`: `labelAddComputerGroupsHelp`
- `0x90783`: `labelAddComputerGroupsHelp`
- `0x90794`: `labelChooseComputerHelp`
- `0x907a4`: `labelChooseComputerHelp`
- `0x907b5`: `btnComputerGroups`
- `0x907c5`: `btnComputerGroups`
- `0x907f9`: `btnComputers`
- `0x90809`: `btnComputers`
- `0x9083d`: `rdAllowedComputers`
- `0x9084d`: `rdAllowedComputers`
- `0x9088d`: `rdAddComputers`
- `0x908a9`: `rdAddComputers`

## pseudocode

```c

```

## disassembly

```asm
0x901b0  ldarg.0
0x901b1  newobj   instance void [System]System.ComponentModel.Container::.ctor()
0x901b6  stfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::components
0x901bb  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog
0x901c0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x901c5  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x901ca  stloc.0
0x901cb  ldarg.0
0x901cc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x901d1  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::okButton
0x901d6  ldarg.0
0x901d7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x901dc  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::cancelButton
0x901e1  ldarg.0
0x901e2  ldarg.0
0x901e3  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::components
0x901e8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip::.ctor(class [System]System.ComponentModel.IContainer)
0x901ed  stfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterContextMenuStrip
0x901f2  ldarg.0
0x901f3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0x901f8  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::editToolStripMenuItem
0x901fd  ldarg.0
0x901fe  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0x90203  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::copyExistingViewToolStripMenuItem
0x90208  ldarg.0
0x90209  newobj   instance void [System.Windows.Forms]System.Windows.Forms.OpenFileDialog::.ctor()
0x9020e  stfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::openViewFileDialog
0x90213  ldarg.0
0x90214  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x90219  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelAccount
0x9021e  ldarg.0
0x9021f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x90224  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelSecurity
0x90229  ldarg.0
0x9022a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x9022f  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelAdditionalSettings
0x90234  ldarg.0
0x90235  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x9023a  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterConfiguredLabel
0x9023f  ldarg.0
0x90240  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x90245  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelConfigureFilter
0x9024a  ldarg.0
0x9024b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x90250  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::advancedButton
0x90255  ldarg.0
0x90256  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x9025b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelDescription
0x90260  ldarg.0
0x90261  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x90266  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::textBoxDescription
0x9026b  ldarg.0
0x9026c  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.ComboBoxWithHScroll::.ctor()
0x90271  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.ComboBoxWithHScroll Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::logComboBox
0x90276  ldarg.0
0x90277  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x9027c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::logNameLabel
0x90281  ldarg.0
0x90282  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x90287  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::textBoxName
0x9028c  ldarg.0
0x9028d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x90292  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::subscriptionNameLabel
0x90297  ldarg.0
0x90298  ldarg.0
0x90299  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::components
0x9029e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolTip::.ctor(class [System]System.ComponentModel.IContainer)
0x902a3  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolTip Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::toolTip1
0x902a8  ldarg.0
0x902a9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x902ae  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::groupBox1
0x902b3  ldarg.0
0x902b4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x902b9  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelAddComputerGroupsHelp
0x902be  ldarg.0
0x902bf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x902c4  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelChooseComputerHelp
0x902c9  ldarg.0
0x902ca  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x902cf  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::btnComputerGroups
0x902d4  ldarg.0
0x902d5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x902da  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::btnComputers
0x902df  ldarg.0
0x902e0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x902e5  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::rdAllowedComputers
0x902ea  ldarg.0
0x902eb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x902f0  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::rdAddComputers
0x902f5  ldarg.0
0x902f6  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.SplitButton::.ctor()
0x902fb  stfld    class Microsoft.Windows.ManagementUI.CombinedControls.SplitButton Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterButton
0x90300  ldarg.0
0x90301  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterContextMenuStrip
0x90306  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9030b  ldarg.0
0x9030c  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::groupBox1
0x90311  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x90316  ldarg.0
0x90317  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x9031c  ldloc.0
0x9031d  ldarg.0
0x9031e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::okButton
0x90323  ldstr    aOkbutton// "okButton"
0x90328  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9032d  ldarg.0
0x9032e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::okButton
0x90333  ldstr    aOkbutton// "okButton"
0x90338  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x9033d  ldarg.0
0x9033e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::okButton
0x90343  ldc.i4.1
0x90344  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x90349  ldarg.0
0x9034a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::okButton
0x9034f  ldarg.0
0x90350  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::okButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x90356  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x9035b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x90360  ldloc.0
0x90361  ldarg.0
0x90362  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::cancelButton
0x90367  ldstr    aCancelbutton// "cancelButton"
0x9036c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x90371  ldarg.0
0x90372  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::cancelButton
0x90377  ldc.i4.2
0x90378  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x9037d  ldarg.0
0x9037e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::cancelButton
0x90383  ldstr    aCancelbutton// "cancelButton"
0x90388  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x9038d  ldarg.0
0x9038e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::cancelButton
0x90393  ldc.i4.1
0x90394  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x90399  ldarg.0
0x9039a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::cancelButton
0x9039f  ldarg.0
0x903a0  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::cancelButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x903a6  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x903ab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x903b0  ldarg.0
0x903b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterContextMenuStrip
0x903b6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0x903bb  ldc.i4.2
0x903bc  newarr   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0x903c1  dup
0x903c2  ldc.i4.0
0x903c3  ldarg.0
0x903c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::editToolStripMenuItem
0x903c9  stelem.ref
0x903ca  dup
0x903cb  ldc.i4.1
0x903cc  ldarg.0
0x903cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::copyExistingViewToolStripMenuItem
0x903d2  stelem.ref
0x903d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem[])
0x903d8  ldarg.0
0x903d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterContextMenuStrip
0x903de  ldstr    aFiltercontextm// "filterContextMenuStrip"
0x903e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x903e8  ldloc.0
0x903e9  ldarg.0
0x903ea  ldfld    class [System.Windows.Forms]System.Windows.Forms.ContextMenuStrip Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterContextMenuStrip
0x903ef  ldstr    aFiltercontextm// "filterContextMenuStrip"
0x903f4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x903f9  ldarg.0
0x903fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::editToolStripMenuItem
0x903ff  ldstr    aEdittoolstripm// "editToolStripMenuItem"
0x90404  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0x90409  ldloc.0
0x9040a  ldarg.0
0x9040b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::editToolStripMenuItem
0x90410  ldstr    aEdittoolstripm// "editToolStripMenuItem"
0x90415  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9041a  ldarg.0
0x9041b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::editToolStripMenuItem
0x90420  ldarg.0
0x90421  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x90427  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x9042c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0x90431  ldarg.0
0x90432  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::copyExistingViewToolStripMenuItem
0x90437  ldstr    aCopyexistingvi// "copyExistingViewToolStripMenuItem"
0x9043c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0x90441  ldloc.0
0x90442  ldarg.0
0x90443  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::copyExistingViewToolStripMenuItem
0x90448  ldstr    aCopyexistingvi// "copyExistingViewToolStripMenuItem"
0x9044d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x90452  ldarg.0
0x90453  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::copyExistingViewToolStripMenuItem
0x90458  ldarg.0
0x90459  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::copyExistingViewToolStripMenuItem_Click(object sender, class [mscorlib]System.EventArgs e)
0x9045f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x90464  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0x90469  ldarg.0
0x9046a  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::openViewFileDialog
0x9046f  ldc.i4.1
0x90470  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x90475  ldloc.0
0x90476  ldarg.0
0x90477  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelAccount
0x9047c  ldstr    aLabelaccount// "labelAccount"
0x90481  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x90486  ldarg.0
0x90487  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelAccount
0x9048c  ldstr    aLabelaccount// "labelAccount"
0x90491  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x90496  ldloc.0
0x90497  ldarg.0
0x90498  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelSecurity
0x9049d  ldstr    aLabelsecurity// "labelSecurity"
0x904a2  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x904a7  ldarg.0
0x904a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelSecurity
0x904ad  ldstr    aLabelsecurity// "labelSecurity"
0x904b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x904b7  ldloc.0
0x904b8  ldarg.0
0x904b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelAdditionalSettings
0x904be  ldstr    aLabeladditiona// "labelAdditionalSettings"
0x904c3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x904c8  ldarg.0
0x904c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelAdditionalSettings
0x904ce  ldstr    aLabeladditiona// "labelAdditionalSettings"
0x904d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x904d8  ldloc.0
0x904d9  ldarg.0
0x904da  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterConfiguredLabel
0x904df  ldstr    aFilterconfigur// "filterConfiguredLabel"
0x904e4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x904e9  ldarg.0
0x904ea  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::filterConfiguredLabel
0x904ef  ldstr    aFilterconfigur// "filterConfiguredLabel"
0x904f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x904f9  ldloc.0
0x904fa  ldarg.0
0x904fb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelConfigureFilter
0x90500  ldstr    aLabelconfigure// "labelConfigureFilter"
0x90505  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9050a  ldarg.0
0x9050b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelConfigureFilter
0x90510  ldstr    aLabelconfigure// "labelConfigureFilter"
0x90515  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x9051a  ldloc.0
0x9051b  ldarg.0
0x9051c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::advancedButton
0x90521  ldstr    aAdvancedbutton// "advancedButton"
0x90526  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9052b  ldarg.0
0x9052c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::advancedButton
0x90531  ldc.i4.1
0x90532  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_AutoEllipsis(bool)
0x90537  ldarg.0
0x90538  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::advancedButton
0x9053d  ldstr    aAdvancedbutton// "advancedButton"
0x90542  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x90547  ldarg.0
0x90548  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::advancedButton
0x9054d  ldc.i4.1
0x9054e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x90553  ldarg.0
0x90554  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::advancedButton
0x90559  ldarg.0
0x9055a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::advancedButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x90560  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x90565  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x9056a  ldloc.0
0x9056b  ldarg.0
0x9056c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelDescription
0x90571  ldstr    aLabeldescripti// "labelDescription"
0x90576  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9057b  ldarg.0
0x9057c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::labelDescription
0x90581  ldstr    aLabeldescripti// "labelDescription"
0x90586  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x9058b  ldloc.0
0x9058c  ldarg.0
0x9058d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::textBoxDescription
0x90592  ldstr    aTextboxdescrip// "textBoxDescription"
0x90597  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x9059c  ldarg.0
0x9059d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::textBoxDescription
0x905a2  ldstr    aTextboxdescrip// "textBoxDescription"
0x905a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x905ac  ldarg.0
0x905ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::textBoxDescription
0x905b2  ldarg.0
0x905b3  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::textBoxDescription_Leave(object sender, class [mscorlib]System.EventArgs e)
0x905b9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x905be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Leave(class [mscorlib]System.EventHandler)
0x905c3  ldarg.0
0x905c4  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ComboBoxWithHScroll Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::logComboBox
0x905c9  ldc.i4.2
0x905ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x905cf  ldarg.0
0x905d0  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.ComboBoxWithHScroll Microsoft.Windows.ManagementUI.CombinedControls.SubscriptionPropertiesDialog::logComboBox
0x905d5  ldc.i4.1
  ... truncated ...
```
