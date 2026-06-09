# Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::InitializeComponent

- ea: `0x88c40`
- end: `0x88fe6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::InitializeComponent`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x88a00`

## string_xrefs

- `0x88f68`: `checkBoxOpenPropertyPage`
- `0x88f8a`: `checkBoxOpenPropertyPage`
- `0x88fbd`: `WizardTaskFinishControl`

## pseudocode

```c

```

## disassembly

```asm
0x88c40  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl
0x88c45  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x88c4a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x88c4f  ldarg.0
0x88c50  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x88c55  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88c5a  ldarg.0
0x88c5b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x88c60  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxAction
0x88c65  ldarg.0
0x88c66  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x88c6b  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxTrigger
0x88c70  ldarg.0
0x88c71  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88c76  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelName
0x88c7b  ldarg.0
0x88c7c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88c81  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label1
0x88c86  ldarg.0
0x88c87  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88c8c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelTrigger
0x88c91  ldarg.0
0x88c92  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88c97  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelAction
0x88c9c  ldarg.0
0x88c9d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x88ca2  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxName
0x88ca7  ldarg.0
0x88ca8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x88cad  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxDescription
0x88cb2  ldarg.0
0x88cb3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x88cb8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label
0x88cbd  ldarg.0
0x88cbe  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x88cc3  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::checkBoxOpenPropertyPage
0x88cc8  ldarg.0
0x88cc9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88cce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x88cd3  ldarg.0
0x88cd4  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x88cd9  dup
0x88cda  ldarg.0
0x88cdb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88ce0  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x88ce5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88cea  ldarg.0
0x88ceb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88cf0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88cf5  ldarg.0
0x88cf6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxAction
0x88cfb  ldc.i4.1
0x88cfc  ldc.i4.3
0x88cfd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88d02  ldarg.0
0x88d03  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88d08  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88d0d  ldarg.0
0x88d0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxTrigger
0x88d13  ldc.i4.1
0x88d14  ldc.i4.2
0x88d15  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88d1a  ldarg.0
0x88d1b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88d20  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88d25  ldarg.0
0x88d26  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelName
0x88d2b  ldc.i4.0
0x88d2c  ldc.i4.0
0x88d2d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88d32  ldarg.0
0x88d33  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88d38  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88d3d  ldarg.0
0x88d3e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label1
0x88d43  ldc.i4.0
0x88d44  ldc.i4.1
0x88d45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88d4a  ldarg.0
0x88d4b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88d50  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88d55  ldarg.0
0x88d56  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelTrigger
0x88d5b  ldc.i4.0
0x88d5c  ldc.i4.2
0x88d5d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88d62  ldarg.0
0x88d63  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88d68  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88d6d  ldarg.0
0x88d6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelAction
0x88d73  ldc.i4.0
0x88d74  ldc.i4.3
0x88d75  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88d7a  ldarg.0
0x88d7b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88d80  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88d85  ldarg.0
0x88d86  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxName
0x88d8b  ldc.i4.1
0x88d8c  ldc.i4.0
0x88d8d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88d92  ldarg.0
0x88d93  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88d98  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88d9d  ldarg.0
0x88d9e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxDescription
0x88da3  ldc.i4.1
0x88da4  ldc.i4.1
0x88da5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88daa  ldarg.0
0x88dab  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88db0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88db5  ldarg.0
0x88db6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label
0x88dbb  ldc.i4.0
0x88dbc  ldc.i4.5
0x88dbd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88dc2  ldarg.0
0x88dc3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88dc8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x88dcd  ldarg.0
0x88dce  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::checkBoxOpenPropertyPage
0x88dd3  ldc.i4.0
0x88dd4  ldc.i4.4
0x88dd5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x88dda  ldarg.0
0x88ddb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88de0  ldc.i4.0
0x88de1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::set_GrowStyle(valuetype [System.Windows.Forms]System.Windows.Forms.TableLayoutPanelGrowStyle)
0x88de6  ldarg.0
0x88de7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88dec  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x88df1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88df6  dup
0x88df7  ldarg.0
0x88df8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxAction
0x88dfd  ldstr    aTextboxaction// "textBoxAction"
0x88e02  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88e07  ldarg.0
0x88e08  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxAction
0x88e0d  ldstr    aTextboxaction// "textBoxAction"
0x88e12  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88e17  ldarg.0
0x88e18  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxAction
0x88e1d  ldc.i4.1
0x88e1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x88e23  dup
0x88e24  ldarg.0
0x88e25  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxTrigger
0x88e2a  ldstr    aTextboxtrigger// "textBoxTrigger"
0x88e2f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88e34  ldarg.0
0x88e35  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxTrigger
0x88e3a  ldstr    aTextboxtrigger// "textBoxTrigger"
0x88e3f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88e44  ldarg.0
0x88e45  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxTrigger
0x88e4a  ldc.i4.1
0x88e4b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x88e50  dup
0x88e51  ldarg.0
0x88e52  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelName
0x88e57  ldstr    aLabelname// "labelName"
0x88e5c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88e61  ldarg.0
0x88e62  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelName
0x88e67  ldstr    aLabelname// "labelName"
0x88e6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88e71  dup
0x88e72  ldarg.0
0x88e73  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label1
0x88e78  ldstr    aLabel1// "label1"
0x88e7d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88e82  ldarg.0
0x88e83  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label1
0x88e88  ldstr    aLabel1// "label1"
0x88e8d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88e92  dup
0x88e93  ldarg.0
0x88e94  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelTrigger
0x88e99  ldstr    aLabeltrigger// "labelTrigger"
0x88e9e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88ea3  ldarg.0
0x88ea4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelTrigger
0x88ea9  ldstr    aLabeltrigger// "labelTrigger"
0x88eae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88eb3  dup
0x88eb4  ldarg.0
0x88eb5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelAction
0x88eba  ldstr    aLabelaction// "labelAction"
0x88ebf  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88ec4  ldarg.0
0x88ec5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::labelAction
0x88eca  ldstr    aLabelaction// "labelAction"
0x88ecf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88ed4  dup
0x88ed5  ldarg.0
0x88ed6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxName
0x88edb  ldstr    aTextboxname// "textBoxName"
0x88ee0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88ee5  ldarg.0
0x88ee6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxName
0x88eeb  ldstr    aTextboxname// "textBoxName"
0x88ef0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88ef5  ldarg.0
0x88ef6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxName
0x88efb  ldc.i4.1
0x88efc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x88f01  dup
0x88f02  ldarg.0
0x88f03  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxDescription
0x88f08  ldstr    aTextboxdescrip// "textBoxDescription"
0x88f0d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88f12  ldarg.0
0x88f13  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxDescription
0x88f18  ldstr    aTextboxdescrip// "textBoxDescription"
0x88f1d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88f22  ldarg.0
0x88f23  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::textBoxDescription
0x88f28  ldc.i4.1
0x88f29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x88f2e  ldarg.0
0x88f2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88f34  ldarg.0
0x88f35  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label
0x88f3a  ldc.i4.2
0x88f3b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x88f40  dup
0x88f41  ldarg.0
0x88f42  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label
0x88f47  ldstr    aLabel// "label"
0x88f4c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88f51  ldarg.0
0x88f52  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::label
0x88f57  ldstr    aLabel// "label"
0x88f5c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88f61  dup
0x88f62  ldarg.0
0x88f63  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::checkBoxOpenPropertyPage
0x88f68  ldstr    aCheckboxopenpr// "checkBoxOpenPropertyPage"
0x88f6d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88f72  ldarg.0
0x88f73  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88f78  ldarg.0
0x88f79  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::checkBoxOpenPropertyPage
0x88f7e  ldc.i4.2
0x88f7f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x88f84  ldarg.0
0x88f85  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::checkBoxOpenPropertyPage
0x88f8a  ldstr    aCheckboxopenpr// "checkBoxOpenPropertyPage"
0x88f8f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88f94  ldarg.0
0x88f95  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::checkBoxOpenPropertyPage
0x88f9a  ldc.i4.1
0x88f9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_UseVisualStyleBackColor(bool)
0x88fa0  ldarg.0
0x88fa1  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x88fa6  ldarg.0
0x88fa7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88fac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x88fb1  ldarg.0
0x88fb2  ldstr    aThis// "$this"
0x88fb7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x88fbc  ldarg.0
0x88fbd  ldstr    aWizardtaskfini// "WizardTaskFinishControl"
0x88fc2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x88fc7  ldarg.0
0x88fc8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88fcd  ldc.i4.0
0x88fce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x88fd3  ldarg.0
0x88fd4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.WizardTaskFinishControl::tableLayoutPanel
0x88fd9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x88fde  ldarg.0
0x88fdf  ldc.i4.0
0x88fe0  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x88fe5  ret
```
