# Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::InitializeComponent

- ea: `0x744c0`
- end: `0x74db4`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::InitializeComponent`
- size: `2292`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x73bb0`

## string_xrefs

- `0x74755`: `labelDescriptionGeneralTaskInfo`
- `0x74777`: `labelDescriptionGeneralTaskInfo`
- `0x74826`: `labelTaskName`
- `0x74848`: `labelTaskName`
- `0x748ab`: `comboBoxVersion`
- `0x748d3`: `comboBoxVersion`
- `0x74a92`: `tableLayoutPanelSecurity`
- `0x74b92`: `tableLayoutPanelSecurity`
- `0x74bd6`: `labelRunWithHighestPrivileges`
- `0x74bf8`: `labelRunWithHighestPrivileges`
- `0x74d45`: `ControlTaskGeneralPreview`

## pseudocode

```c

```

## disassembly

```asm
0x744c0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview
0x744c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x744ca  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x744cf  ldarg.0
0x744d0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x744d5  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelAuthorText
0x744da  ldarg.0
0x744db  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x744e0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelAuthor
0x744e5  ldarg.0
0x744e6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x744eb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTextBoxUser
0x744f0  ldarg.0
0x744f1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x744f6  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxS4U
0x744fb  ldarg.0
0x744fc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x74501  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxRunElevated
0x74506  ldarg.0
0x74507  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x7450c  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::radioButtonUserLoggedOnOrNot
0x74511  ldarg.0
0x74512  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x74517  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::radioButtonLoggedOnUser
0x7451c  ldarg.0
0x7451d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x74522  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelDescriptionGeneralTaskInfo
0x74527  ldarg.0
0x74528  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x7452d  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxDescription
0x74532  ldarg.0
0x74533  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x74538  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxName
0x7453d  ldarg.0
0x7453e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x74543  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTaskName
0x74548  ldarg.0
0x74549  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7454e  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxHidden
0x74553  ldarg.0
0x74554  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x74559  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelVersion
0x7455e  ldarg.0
0x7455f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x74564  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x74569  ldarg.0
0x7456a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x7456f  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
0x74574  ldarg.0
0x74575  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x7457a  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::groupBoxUserOptions
0x7457f  ldarg.0
0x74580  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x74585  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelSecurity
0x7458a  ldarg.0
0x7458b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x74590  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelUserDescription
0x74595  ldarg.0
0x74596  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7459b  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelRunWithHighestPrivileges
0x745a0  ldarg.0
0x745a1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x745a6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelS4U
0x745ab  ldarg.0
0x745ac  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x745b1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelUserLoggedOnOrNot
0x745b6  ldarg.0
0x745b7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x745bc  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelLoggedOnUser
0x745c1  ldarg.0
0x745c2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x745c7  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelHidden
0x745cc  ldarg.0
0x745cd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x745d2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelLocation
0x745d7  ldarg.0
0x745d8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x745dd  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxLocation
0x745e2  ldarg.0
0x745e3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
0x745e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x745ed  ldarg.0
0x745ee  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::groupBoxUserOptions
0x745f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x745f8  ldarg.0
0x745f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelSecurity
0x745fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x74603  ldarg.0
0x74604  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x74609  dup
0x7460a  ldarg.0
0x7460b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelAuthorText
0x74610  ldstr    aLabelauthortex// "labelAuthorText"
0x74615  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7461a  ldarg.0
0x7461b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
0x74620  ldarg.0
0x74621  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelAuthorText
0x74626  ldc.i4.3
0x74627  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7462c  ldarg.0
0x7462d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelAuthorText
0x74632  ldstr    aLabelauthortex// "labelAuthorText"
0x74637  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7463c  dup
0x7463d  ldarg.0
0x7463e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelAuthor
0x74643  ldstr    aLabelauthor// "labelAuthor"
0x74648  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7464d  ldarg.0
0x7464e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
0x74653  ldarg.0
0x74654  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelAuthor
0x74659  ldc.i4.2
0x7465a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x7465f  ldarg.0
0x74660  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelAuthor
0x74665  ldstr    aLabelauthor// "labelAuthor"
0x7466a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7466f  dup
0x74670  ldarg.0
0x74671  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTextBoxUser
0x74676  ldstr    aLabeltextboxus// "labelTextBoxUser"
0x7467b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x74680  ldarg.0
0x74681  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTextBoxUser
0x74686  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x7468b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x74690  ldarg.0
0x74691  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelSecurity
0x74696  ldarg.0
0x74697  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTextBoxUser
0x7469c  ldc.i4.3
0x7469d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x746a2  ldarg.0
0x746a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTextBoxUser
0x746a8  ldstr    aLabeltextboxus// "labelTextBoxUser"
0x746ad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x746b2  dup
0x746b3  ldarg.0
0x746b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxS4U
0x746b9  ldstr    aCheckboxs4u// "checkBoxS4U"
0x746be  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x746c3  ldarg.0
0x746c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxS4U
0x746c9  ldstr    aCheckboxs4u// "checkBoxS4U"
0x746ce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x746d3  dup
0x746d4  ldarg.0
0x746d5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxRunElevated
0x746da  ldstr    aCheckboxrunele// "checkBoxRunElevated"
0x746df  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x746e4  ldarg.0
0x746e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxRunElevated
0x746ea  ldstr    aCheckboxrunele// "checkBoxRunElevated"
0x746ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x746f4  dup
0x746f5  ldarg.0
0x746f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::radioButtonUserLoggedOnOrNot
0x746fb  ldstr    aRadiobuttonuse// "radioButtonUserLoggedOnOrNot"
0x74700  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x74705  ldarg.0
0x74706  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::radioButtonUserLoggedOnOrNot
0x7470b  ldstr    aRadiobuttonuse// "radioButtonUserLoggedOnOrNot"
0x74710  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x74715  dup
0x74716  ldarg.0
0x74717  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::radioButtonLoggedOnUser
0x7471c  ldstr    aRadiobuttonlog// "radioButtonLoggedOnUser"
0x74721  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x74726  ldarg.0
0x74727  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::radioButtonLoggedOnUser
0x7472c  ldc.i4.1
0x7472d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0x74732  ldarg.0
0x74733  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::radioButtonLoggedOnUser
0x74738  ldstr    aRadiobuttonlog// "radioButtonLoggedOnUser"
0x7473d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x74742  ldarg.0
0x74743  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::radioButtonLoggedOnUser
0x74748  ldc.i4.1
0x74749  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_TabStop(bool)
0x7474e  dup
0x7474f  ldarg.0
0x74750  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelDescriptionGeneralTaskInfo
0x74755  ldstr    aLabeldescripti_4// "labelDescriptionGeneralTaskInfo"
0x7475a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x7475f  ldarg.0
0x74760  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
0x74765  ldarg.0
0x74766  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelDescriptionGeneralTaskInfo
0x7476b  ldc.i4.2
0x7476c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x74771  ldarg.0
0x74772  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelDescriptionGeneralTaskInfo
0x74777  ldstr    aLabeldescripti_4// "labelDescriptionGeneralTaskInfo"
0x7477c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x74781  ldarg.0
0x74782  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxDescription
0x74787  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x7478c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x74791  ldarg.0
0x74792  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
0x74797  ldarg.0
0x74798  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxDescription
0x7479d  ldc.i4.3
0x7479e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x747a3  dup
0x747a4  ldarg.0
0x747a5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxDescription
0x747aa  ldstr    aTextboxdescrip// "textBoxDescription"
0x747af  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x747b4  ldarg.0
0x747b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxDescription
0x747ba  ldstr    aTextboxdescrip// "textBoxDescription"
0x747bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x747c4  ldarg.0
0x747c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxDescription
0x747ca  ldc.i4.1
0x747cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x747d0  ldarg.0
0x747d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxName
0x747d6  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x747db  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x747e0  ldarg.0
0x747e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
0x747e6  ldarg.0
0x747e7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxName
0x747ec  ldc.i4.3
0x747ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x747f2  dup
0x747f3  ldarg.0
0x747f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxName
0x747f9  ldstr    aTextboxname// "textBoxName"
0x747fe  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x74803  ldarg.0
0x74804  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxName
0x74809  ldstr    aTextboxname// "textBoxName"
0x7480e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x74813  ldarg.0
0x74814  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::textBoxName
0x74819  ldc.i4.1
0x7481a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x7481f  dup
0x74820  ldarg.0
0x74821  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTaskName
0x74826  ldstr    aLabeltaskname// "labelTaskName"
0x7482b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x74830  ldarg.0
0x74831  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
0x74836  ldarg.0
0x74837  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTaskName
0x7483c  ldc.i4.2
0x7483d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x74842  ldarg.0
0x74843  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelTaskName
0x74848  ldstr    aLabeltaskname// "labelTaskName"
0x7484d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x74852  dup
0x74853  ldarg.0
0x74854  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxHidden
0x74859  ldstr    aCheckboxhidden// "checkBoxHidden"
0x7485e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x74863  ldarg.0
0x74864  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::checkBoxHidden
0x74869  ldstr    aCheckboxhidden// "checkBoxHidden"
0x7486e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x74873  dup
0x74874  ldarg.0
0x74875  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelVersion
0x7487a  ldstr    aLabelversion// "labelVersion"
0x7487f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x74884  ldarg.0
0x74885  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::labelVersion
0x7488a  ldstr    aLabelversion// "labelVersion"
0x7488f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x74894  ldarg.0
0x74895  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x7489a  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x7489f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x748a4  dup
0x748a5  ldarg.0
0x748a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x748ab  ldstr    aComboboxversio// "comboBoxVersion"
0x748b0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x748b5  ldarg.0
0x748b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x748bb  ldc.i4.2
0x748bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x748c1  ldarg.0
0x748c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x748c7  ldc.i4.1
0x748c8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x748cd  ldarg.0
0x748ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::comboBoxVersion
0x748d3  ldstr    aComboboxversio// "comboBoxVersion"
0x748d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x748dd  dup
0x748de  ldarg.0
0x748df  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.ControlTaskGeneralPreview::tableLayoutPanelGeneral
  ... truncated ...
```
