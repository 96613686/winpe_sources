# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::InitializeComponent

- ea: `0x732d0`
- end: `0x73b25`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::InitializeComponent`
- size: `2133`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x72280`

## string_xrefs

- `0x73603`: `labelDescriptionGeneralTaskInfo`
- `0x73613`: `labelDescriptionGeneralTaskInfo`
- `0x736d8`: `labelTaskName`
- `0x736e8`: `labelTaskName`
- `0x73752`: `comboBoxVersion`
- `0x7377a`: `comboBoxVersion`
- `0x73938`: `tableLayoutPanelSecurity`
- `0x739f0`: `tableLayoutPanelSecurity`
- `0x73ab6`: `ControlTaskGeneralInfo`

## pseudocode

```c

```

## disassembly

```asm
0x732d0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo
0x732d5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x732da  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x732df  ldarg.0
0x732e0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x732e5  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelAuthorText
0x732ea  ldarg.0
0x732eb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x732f0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelAuthor
0x732f5  ldarg.0
0x732f6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x732fb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelTextBoxUser
0x73300  ldarg.0
0x73301  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x73306  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::buttonSetUserOrGroup
0x7330b  ldarg.0
0x7330c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x73311  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxS4U
0x73316  ldarg.0
0x73317  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7331c  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxRunElevated
0x73321  ldarg.0
0x73322  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x73327  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonUserLoggedOnOrNot
0x7332c  ldarg.0
0x7332d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x73332  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonLoggedOnUser
0x73337  ldarg.0
0x73338  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7333d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelDescriptionGeneralTaskInfo
0x73342  ldarg.0
0x73343  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x73348  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxDescription
0x7334d  ldarg.0
0x7334e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x73353  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName
0x73358  ldarg.0
0x73359  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7335e  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelTaskName
0x73363  ldarg.0
0x73364  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x73369  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxHidden
0x7336e  ldarg.0
0x7336f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x73374  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelVersion
0x73379  ldarg.0
0x7337a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x7337f  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::comboBoxVersion
0x73384  ldarg.0
0x73385  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x7338a  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelGeneral
0x7338f  ldarg.0
0x73390  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x73395  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::groupBoxUserOptions
0x7339a  ldarg.0
0x7339b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x733a0  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelSecurity
0x733a5  ldarg.0
0x733a6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x733ab  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelUserDescription
0x733b0  ldarg.0
0x733b1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x733b6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelLocation
0x733bb  ldarg.0
0x733bc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x733c1  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxLocation
0x733c6  ldarg.0
0x733c7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelGeneral
0x733cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x733d1  ldarg.0
0x733d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::groupBoxUserOptions
0x733d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x733dc  ldarg.0
0x733dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelSecurity
0x733e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x733e7  ldarg.0
0x733e8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x733ed  dup
0x733ee  ldarg.0
0x733ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelAuthorText
0x733f4  ldstr    aLabelauthortex// "labelAuthorText"
0x733f9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x733fe  ldarg.0
0x733ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelGeneral
0x73404  ldarg.0
0x73405  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelAuthorText
0x7340a  ldc.i4.3
0x7340b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x73410  ldarg.0
0x73411  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelAuthorText
0x73416  ldstr    aLabelauthortex// "labelAuthorText"
0x7341b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x73420  dup
0x73421  ldarg.0
0x73422  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelAuthor
0x73427  ldstr    aLabelauthor// "labelAuthor"
0x7342c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x73431  ldarg.0
0x73432  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelAuthor
0x73437  ldstr    aLabelauthor// "labelAuthor"
0x7343c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x73441  dup
0x73442  ldarg.0
0x73443  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelTextBoxUser
0x73448  ldstr    aLabeltextboxus// "labelTextBoxUser"
0x7344d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x73452  ldarg.0
0x73453  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelTextBoxUser
0x73458  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x7345d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x73462  ldarg.0
0x73463  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelSecurity
0x73468  ldarg.0
0x73469  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelTextBoxUser
0x7346e  ldc.i4.2
0x7346f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x73474  ldarg.0
0x73475  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelTextBoxUser
0x7347a  ldstr    aLabeltextboxus// "labelTextBoxUser"
0x7347f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x73484  dup
0x73485  ldarg.0
0x73486  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::buttonSetUserOrGroup
0x7348b  ldstr    aButtonsetusero// "buttonSetUserOrGroup"
0x73490  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x73495  ldarg.0
0x73496  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::buttonSetUserOrGroup
0x7349b  ldstr    aButtonsetusero// "buttonSetUserOrGroup"
0x734a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x734a5  ldarg.0
0x734a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::buttonSetUserOrGroup
0x734ab  ldarg.0
0x734ac  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::buttonSetUserOrGroup_Click(object sender, class [mscorlib]System.EventArgs e)
0x734b2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x734b7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x734bc  dup
0x734bd  ldarg.0
0x734be  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxS4U
0x734c3  ldstr    aCheckboxs4u// "checkBoxS4U"
0x734c8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x734cd  ldarg.0
0x734ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelSecurity
0x734d3  ldarg.0
0x734d4  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxS4U
0x734d9  ldc.i4.2
0x734da  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x734df  ldarg.0
0x734e0  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxS4U
0x734e5  ldstr    aCheckboxs4u// "checkBoxS4U"
0x734ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x734ef  ldarg.0
0x734f0  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxS4U
0x734f5  ldarg.0
0x734f6  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxS4U_Click(object sender, class [mscorlib]System.EventArgs e)
0x734fc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x73501  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x73506  dup
0x73507  ldarg.0
0x73508  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxRunElevated
0x7350d  ldstr    aCheckboxrunele// "checkBoxRunElevated"
0x73512  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x73517  ldarg.0
0x73518  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelSecurity
0x7351d  ldarg.0
0x7351e  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxRunElevated
0x73523  ldc.i4.3
0x73524  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x73529  ldarg.0
0x7352a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxRunElevated
0x7352f  ldstr    aCheckboxrunele// "checkBoxRunElevated"
0x73534  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x73539  ldarg.0
0x7353a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxRunElevated
0x7353f  ldarg.0
0x73540  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxRunElevated_Click(object sender, class [mscorlib]System.EventArgs e)
0x73546  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x7354b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x73550  dup
0x73551  ldarg.0
0x73552  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonUserLoggedOnOrNot
0x73557  ldstr    aRadiobuttonuse// "radioButtonUserLoggedOnOrNot"
0x7355c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x73561  ldarg.0
0x73562  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelSecurity
0x73567  ldarg.0
0x73568  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonUserLoggedOnOrNot
0x7356d  ldc.i4.3
0x7356e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x73573  ldarg.0
0x73574  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonUserLoggedOnOrNot
0x73579  ldstr    aRadiobuttonuse// "radioButtonUserLoggedOnOrNot"
0x7357e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x73583  ldarg.0
0x73584  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonUserLoggedOnOrNot
0x73589  ldarg.0
0x7358a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonUserLoggedOnOrNot_Click(object sender, class [mscorlib]System.EventArgs e)
0x73590  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x73595  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x7359a  dup
0x7359b  ldarg.0
0x7359c  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonLoggedOnUser
0x735a1  ldstr    aRadiobuttonlog// "radioButtonLoggedOnUser"
0x735a6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x735ab  ldarg.0
0x735ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonLoggedOnUser
0x735b1  ldc.i4.1
0x735b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x735b7  ldarg.0
0x735b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelSecurity
0x735bd  ldarg.0
0x735be  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonLoggedOnUser
0x735c3  ldc.i4.3
0x735c4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x735c9  ldarg.0
0x735ca  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonLoggedOnUser
0x735cf  ldstr    aRadiobuttonlog// "radioButtonLoggedOnUser"
0x735d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x735d9  ldarg.0
0x735da  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonLoggedOnUser
0x735df  ldc.i4.1
0x735e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x735e5  ldarg.0
0x735e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonLoggedOnUser
0x735eb  ldarg.0
0x735ec  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::radioButtonLoggedOnUser_Click(object sender, class [mscorlib]System.EventArgs e)
0x735f2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x735f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x735fc  dup
0x735fd  ldarg.0
0x735fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelDescriptionGeneralTaskInfo
0x73603  ldstr    aLabeldescripti_4// "labelDescriptionGeneralTaskInfo"
0x73608  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7360d  ldarg.0
0x7360e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelDescriptionGeneralTaskInfo
0x73613  ldstr    aLabeldescripti_4// "labelDescriptionGeneralTaskInfo"
0x73618  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7361d  ldarg.0
0x7361e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxDescription
0x73623  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0x73628  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x7362d  ldarg.0
0x7362e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelGeneral
0x73633  ldarg.0
0x73634  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxDescription
0x73639  ldc.i4.3
0x7363a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7363f  dup
0x73640  ldarg.0
0x73641  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxDescription
0x73646  ldstr    aTextboxdescrip// "textBoxDescription"
0x7364b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x73650  ldarg.0
0x73651  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxDescription
0x73656  ldstr    aTextboxdescrip// "textBoxDescription"
0x7365b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x73660  ldarg.0
0x73661  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxDescription
0x73666  ldarg.0
0x73667  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxDescription_TextChanged(object sender, class [mscorlib]System.EventArgs e)
0x7366d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x73672  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x73677  ldarg.0
0x73678  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName
0x7367d  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0x73682  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x73687  ldarg.0
0x73688  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::tableLayoutPanelGeneral
0x7368d  ldarg.0
0x7368e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName
0x73693  ldc.i4.3
0x73694  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x73699  dup
0x7369a  ldarg.0
0x7369b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName
0x736a0  ldstr    aTextboxname// "textBoxName"
0x736a5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x736aa  ldarg.0
0x736ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName
0x736b0  ldstr    aTextboxname// "textBoxName"
0x736b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x736ba  ldarg.0
0x736bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName
0x736c0  ldarg.0
0x736c1  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::textBoxName_TextChanged(object sender, class [mscorlib]System.EventArgs e)
0x736c7  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x736cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x736d1  dup
0x736d2  ldarg.0
0x736d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelTaskName
0x736d8  ldstr    aLabeltaskname// "labelTaskName"
0x736dd  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x736e2  ldarg.0
0x736e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::labelTaskName
0x736e8  ldstr    aLabeltaskname// "labelTaskName"
0x736ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x736f2  dup
0x736f3  ldarg.0
0x736f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralInfo::checkBoxHidden
0x736f9  ldstr    aCheckboxhidden// "checkBoxHidden"
0x736fe  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
  ... truncated ...
```
