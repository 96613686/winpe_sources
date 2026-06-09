# Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::InitializeComponent

- ea: `0x8c890`
- end: `0x8d12d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::InitializeComponent`
- size: `2205`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8c050`

## string_xrefs

- `0x8caa2`: `protocolLabel`
- `0x8cab2`: `protocolLabel`
- `0x8cd2e`: `groupBoxSecurity`
- `0x8cd3e`: `groupBoxSecurity`
- `0x8ce12`: `labelSecurity`
- `0x8ce22`: `labelSecurity`
- `0x8cf56`: `protocolComboBox`
- `0x8cf66`: `protocolComboBox`

## pseudocode

```c

```

## disassembly

```asm
0x8c890  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog
0x8c895  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8c89a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x8c89f  ldarg.0
0x8c8a0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8c8a5  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::okButton
0x8c8aa  ldarg.0
0x8c8ab  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8c8b0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::cancelButton
0x8c8b5  ldarg.0
0x8c8b6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x8c8bb  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portTextBox
0x8c8c0  ldarg.0
0x8c8c1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8c8c6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::protocolLabel
0x8c8cb  ldarg.0
0x8c8cc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8c8d1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portLabel
0x8c8d6  ldarg.0
0x8c8d7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x8c8dc  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxEventDeliveryOpti
0x8c8e1  ldarg.0
0x8c8e2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x8c8e7  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8c8ec  ldarg.0
0x8c8ed  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x8c8f2  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonCustom
0x8c8f7  ldarg.0
0x8c8f8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x8c8fd  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonNormal
0x8c902  ldarg.0
0x8c903  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x8c908  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinimizeLatency
0x8c90d  ldarg.0
0x8c90e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x8c913  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinBandwidth
0x8c918  ldarg.0
0x8c919  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x8c91e  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxSecurity
0x8c923  ldarg.0
0x8c924  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x8c929  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelUserAccount
0x8c92e  ldarg.0
0x8c92f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8c934  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::labelSecurity
0x8c939  ldarg.0
0x8c93a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x8c93f  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMachineAccount
0x8c944  ldarg.0
0x8c945  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8c94a  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::buttonPassword
0x8c94f  ldarg.0
0x8c950  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8c955  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::labelAccount
0x8c95a  ldarg.0
0x8c95b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x8c960  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonUser
0x8c965  ldarg.0
0x8c966  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x8c96b  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::protocolComboBox
0x8c970  ldarg.0
0x8c971  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x8c976  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanel
0x8c97b  ldarg.0
0x8c97c  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxEventDeliveryOpti
0x8c981  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8c986  ldarg.0
0x8c987  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8c98c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8c991  ldarg.0
0x8c992  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxSecurity
0x8c997  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8c99c  ldarg.0
0x8c99d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelUserAccount
0x8c9a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8c9a7  ldarg.0
0x8c9a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanel
0x8c9ad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8c9b2  ldarg.0
0x8c9b3  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8c9b8  dup
0x8c9b9  ldarg.0
0x8c9ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::okButton
0x8c9bf  ldstr    aOkbutton// "okButton"
0x8c9c4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8c9c9  ldarg.0
0x8c9ca  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::okButton
0x8c9cf  ldstr    aOkbutton// "okButton"
0x8c9d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8c9d9  ldarg.0
0x8c9da  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::okButton
0x8c9df  ldc.i4.1
0x8c9e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8c9e5  ldarg.0
0x8c9e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::okButton
0x8c9eb  ldarg.0
0x8c9ec  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::okButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x8c9f2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8c9f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x8c9fc  dup
0x8c9fd  ldarg.0
0x8c9fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::cancelButton
0x8ca03  ldstr    aCancelbutton// "cancelButton"
0x8ca08  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8ca0d  ldarg.0
0x8ca0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::cancelButton
0x8ca13  ldc.i4.2
0x8ca14  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x8ca19  ldarg.0
0x8ca1a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::cancelButton
0x8ca1f  ldstr    aCancelbutton// "cancelButton"
0x8ca24  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8ca29  ldarg.0
0x8ca2a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::cancelButton
0x8ca2f  ldc.i4.1
0x8ca30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8ca35  ldarg.0
0x8ca36  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::cancelButton
0x8ca3b  ldarg.0
0x8ca3c  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::cancelButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x8ca42  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8ca47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x8ca4c  dup
0x8ca4d  ldarg.0
0x8ca4e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portTextBox
0x8ca53  ldstr    aPorttextbox// "portTextBox"
0x8ca58  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8ca5d  ldarg.0
0x8ca5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portTextBox
0x8ca63  ldstr    aPorttextbox// "portTextBox"
0x8ca68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8ca6d  ldarg.0
0x8ca6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portTextBox
0x8ca73  ldarg.0
0x8ca74  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portTextBox_Leave(object sender, class [mscorlib]System.EventArgs e)
0x8ca7a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8ca7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Leave(class [mscorlib]System.EventHandler)
0x8ca84  ldarg.0
0x8ca85  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portTextBox
0x8ca8a  ldarg.0
0x8ca8b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portTextBox_TextChanged(object sender, class [mscorlib]System.EventArgs e)
0x8ca91  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8ca96  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x8ca9b  dup
0x8ca9c  ldarg.0
0x8ca9d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::protocolLabel
0x8caa2  ldstr    aProtocollabel// "protocolLabel"
0x8caa7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8caac  ldarg.0
0x8caad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::protocolLabel
0x8cab2  ldstr    aProtocollabel// "protocolLabel"
0x8cab7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8cabc  dup
0x8cabd  ldarg.0
0x8cabe  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portLabel
0x8cac3  ldstr    aPortlabel// "portLabel"
0x8cac8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8cacd  ldarg.0
0x8cace  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::portLabel
0x8cad3  ldstr    aPortlabel// "portLabel"
0x8cad8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8cadd  ldarg.0
0x8cade  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanel
0x8cae3  ldarg.0
0x8cae4  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxEventDeliveryOpti
0x8cae9  ldc.i4.5
0x8caea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x8caef  ldarg.0
0x8caf0  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxEventDeliveryOpti
0x8caf5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x8cafa  ldarg.0
0x8cafb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8cb00  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x8cb05  dup
0x8cb06  ldarg.0
0x8cb07  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxEventDeliveryOpti
0x8cb0c  ldstr    aGroupboxeventd// "groupBoxEventDeliveryOpti"
0x8cb11  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8cb16  ldarg.0
0x8cb17  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxEventDeliveryOpti
0x8cb1c  ldstr    aGroupboxeventd// "groupBoxEventDeliveryOpti"
0x8cb21  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8cb26  ldarg.0
0x8cb27  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::groupBoxEventDeliveryOpti
0x8cb2c  ldc.i4.0
0x8cb2d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x8cb32  dup
0x8cb33  ldarg.0
0x8cb34  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8cb39  ldstr    aTablelayoutpan_25// "tableLayoutPanelEventDeliveryOpti"
0x8cb3e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8cb43  ldarg.0
0x8cb44  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8cb49  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8cb4e  ldarg.0
0x8cb4f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonCustom
0x8cb54  ldc.i4.0
0x8cb55  ldc.i4.3
0x8cb56  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8cb5b  ldarg.0
0x8cb5c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8cb61  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8cb66  ldarg.0
0x8cb67  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonNormal
0x8cb6c  ldc.i4.0
0x8cb6d  ldc.i4.0
0x8cb6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8cb73  ldarg.0
0x8cb74  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8cb79  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8cb7e  ldarg.0
0x8cb7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinimizeLatency
0x8cb84  ldc.i4.0
0x8cb85  ldc.i4.2
0x8cb86  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8cb8b  ldarg.0
0x8cb8c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8cb91  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x8cb96  ldarg.0
0x8cb97  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinBandwidth
0x8cb9c  ldc.i4.0
0x8cb9d  ldc.i4.1
0x8cb9e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x8cba3  ldarg.0
0x8cba4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8cba9  ldc.i4.0
0x8cbaa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::set_GrowStyle(valuetype [System.Windows.Forms]System.Windows.Forms.TableLayoutPanelGrowStyle)
0x8cbaf  ldarg.0
0x8cbb0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::tableLayoutPanelEventDeliveryOpti
0x8cbb5  ldstr    aTablelayoutpan_25// "tableLayoutPanelEventDeliveryOpti"
0x8cbba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8cbbf  dup
0x8cbc0  ldarg.0
0x8cbc1  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonCustom
0x8cbc6  ldstr    aRadiobuttoncus// "radioButtonCustom"
0x8cbcb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8cbd0  ldarg.0
0x8cbd1  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonCustom
0x8cbd6  ldstr    aRadiobuttoncus// "radioButtonCustom"
0x8cbdb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8cbe0  ldarg.0
0x8cbe1  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonCustom
0x8cbe6  ldc.i4.1
0x8cbe7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x8cbec  ldarg.0
0x8cbed  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonCustom
0x8cbf2  ldc.i4.1
0x8cbf3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8cbf8  ldarg.0
0x8cbf9  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonCustom
0x8cbfe  ldarg.0
0x8cbff  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonCustom_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x8cc05  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8cc0a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x8cc0f  dup
0x8cc10  ldarg.0
0x8cc11  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonNormal
0x8cc16  ldstr    aRadiobuttonnor// "radioButtonNormal"
0x8cc1b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8cc20  ldarg.0
0x8cc21  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonNormal
0x8cc26  ldstr    aRadiobuttonnor// "radioButtonNormal"
0x8cc2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8cc30  ldarg.0
0x8cc31  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonNormal
0x8cc36  ldc.i4.1
0x8cc37  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x8cc3c  ldarg.0
0x8cc3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonNormal
0x8cc42  ldc.i4.1
0x8cc43  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8cc48  ldarg.0
0x8cc49  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonNormal
0x8cc4e  ldarg.0
0x8cc4f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonNormal_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x8cc55  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8cc5a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x8cc5f  dup
0x8cc60  ldarg.0
0x8cc61  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinimizeLatency
0x8cc66  ldstr    aRadiobuttonmin// "radioButtonMinimizeLatency"
0x8cc6b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x8cc70  ldarg.0
0x8cc71  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinimizeLatency
0x8cc76  ldstr    aRadiobuttonmin// "radioButtonMinimizeLatency"
0x8cc7b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8cc80  ldarg.0
0x8cc81  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinimizeLatency
0x8cc86  ldc.i4.1
0x8cc87  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x8cc8c  ldarg.0
0x8cc8d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinimizeLatency
0x8cc92  ldc.i4.1
0x8cc93  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x8cc98  ldarg.0
0x8cc99  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinimizeLatency
0x8cc9e  ldarg.0
0x8cc9f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AdvancedSubscriptionSettingsDialog::radioButtonMinimizeLatency_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x8cca5  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8ccaa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
  ... truncated ...
```
