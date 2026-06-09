# Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::InitializeComponent

- ea: `0x24c60`
- end: `0x24fca`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::InitializeComponent`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x24a40`

## string_xrefs

- `0x24d95`: `privacyLink`
- `0x24da5`: `privacyLink`

## pseudocode

```c

```

## disassembly

```asm
0x24c60  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg
0x24c65  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24c6a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x24c6f  ldarg.0
0x24c70  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x24c75  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::descriptionLabel
0x24c7a  ldarg.0
0x24c7b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x24c80  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::infoToSendListView
0x24c85  ldarg.0
0x24c86  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x24c8b  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::neverAskAgainCheckBox
0x24c90  ldarg.0
0x24c91  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x24c96  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::privacyLink
0x24c9b  ldarg.0
0x24c9c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x24ca1  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24ca6  ldarg.0
0x24ca7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x24cac  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24cb1  ldarg.0
0x24cb2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x24cb7  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::yesBtn
0x24cbc  ldarg.0
0x24cbd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x24cc2  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::noBtn
0x24cc7  ldarg.0
0x24cc8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24ccd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x24cd2  ldarg.0
0x24cd3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24cd8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x24cdd  ldarg.0
0x24cde  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x24ce3  dup
0x24ce4  ldarg.0
0x24ce5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::descriptionLabel
0x24cea  ldstr    aDescriptionlab// "descriptionLabel"
0x24cef  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24cf4  ldarg.0
0x24cf5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24cfa  ldarg.0
0x24cfb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::descriptionLabel
0x24d00  ldc.i4.3
0x24d01  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x24d06  ldarg.0
0x24d07  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::descriptionLabel
0x24d0c  ldstr    aDescriptionlab// "descriptionLabel"
0x24d11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24d16  dup
0x24d17  ldarg.0
0x24d18  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::infoToSendListView
0x24d1d  ldstr    aInfotosendlist// "infoToSendListView"
0x24d22  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24d27  ldarg.0
0x24d28  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24d2d  ldarg.0
0x24d2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::infoToSendListView
0x24d33  ldc.i4.3
0x24d34  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x24d39  ldarg.0
0x24d3a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::infoToSendListView
0x24d3f  ldc.i4.1
0x24d40  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_FullRowSelect(bool)
0x24d45  ldarg.0
0x24d46  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::infoToSendListView
0x24d4b  ldstr    aInfotosendlist// "infoToSendListView"
0x24d50  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24d55  ldarg.0
0x24d56  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::infoToSendListView
0x24d5b  ldc.i4.0
0x24d5c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_UseCompatibleStateImageBehavior(bool)
0x24d61  ldarg.0
0x24d62  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::infoToSendListView
0x24d67  ldc.i4.1
0x24d68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListView::set_View(valuetype [System.Windows.Forms]System.Windows.Forms.View)
0x24d6d  dup
0x24d6e  ldarg.0
0x24d6f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::neverAskAgainCheckBox
0x24d74  ldstr    aNeveraskagainc// "neverAskAgainCheckBox"
0x24d79  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24d7e  ldarg.0
0x24d7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::neverAskAgainCheckBox
0x24d84  ldstr    aNeveraskagainc// "neverAskAgainCheckBox"
0x24d89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24d8e  dup
0x24d8f  ldarg.0
0x24d90  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::privacyLink
0x24d95  ldstr    aPrivacylink// "privacyLink"
0x24d9a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24d9f  ldarg.0
0x24da0  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::privacyLink
0x24da5  ldstr    aPrivacylink// "privacyLink"
0x24daa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24daf  ldarg.0
0x24db0  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::privacyLink
0x24db5  ldc.i4.1
0x24db6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_TabStop(bool)
0x24dbb  ldarg.0
0x24dbc  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::privacyLink
0x24dc1  ldarg.0
0x24dc2  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::privacyLink_LinkClicked(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0x24dc8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0x24dcd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0x24dd2  dup
0x24dd3  ldarg.0
0x24dd4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24dd9  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x24dde  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24de3  ldarg.0
0x24de4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24de9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x24dee  ldarg.0
0x24def  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24df4  ldc.i4.1
0x24df5  ldc.i4.3
0x24df6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x24dfb  ldarg.0
0x24dfc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24e01  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x24e06  ldarg.0
0x24e07  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::descriptionLabel
0x24e0c  ldc.i4.0
0x24e0d  ldc.i4.0
0x24e0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x24e13  ldarg.0
0x24e14  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24e19  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x24e1e  ldarg.0
0x24e1f  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::neverAskAgainCheckBox
0x24e24  ldc.i4.0
0x24e25  ldc.i4.2
0x24e26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x24e2b  ldarg.0
0x24e2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24e31  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x24e36  ldarg.0
0x24e37  ldfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::privacyLink
0x24e3c  ldc.i4.0
0x24e3d  ldc.i4.3
0x24e3e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x24e43  ldarg.0
0x24e44  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24e49  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x24e4e  ldarg.0
0x24e4f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListView Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::infoToSendListView
0x24e54  ldc.i4.0
0x24e55  ldc.i4.1
0x24e56  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x24e5b  ldarg.0
0x24e5c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24e61  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x24e66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24e6b  dup
0x24e6c  ldarg.0
0x24e6d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24e72  ldstr    aButtonlayoutpa// "buttonLayoutPanel"
0x24e77  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24e7c  ldarg.0
0x24e7d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24e82  ldarg.0
0x24e83  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24e88  ldc.i4.2
0x24e89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x24e8e  ldarg.0
0x24e8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24e94  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x24e99  ldarg.0
0x24e9a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::yesBtn
0x24e9f  ldc.i4.0
0x24ea0  ldc.i4.0
0x24ea1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x24ea6  ldarg.0
0x24ea7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24eac  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x24eb1  ldarg.0
0x24eb2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::noBtn
0x24eb7  ldc.i4.1
0x24eb8  ldc.i4.0
0x24eb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x24ebe  ldarg.0
0x24ebf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24ec4  ldstr    aButtonlayoutpa// "buttonLayoutPanel"
0x24ec9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24ece  dup
0x24ecf  ldarg.0
0x24ed0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::yesBtn
0x24ed5  ldstr    aYesbtn// "yesBtn"
0x24eda  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24edf  ldarg.0
0x24ee0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::yesBtn
0x24ee5  ldstr    aYesbtn// "yesBtn"
0x24eea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24eef  ldarg.0
0x24ef0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::yesBtn
0x24ef5  ldarg.0
0x24ef6  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::yesBtn_Click(object sender, class [mscorlib]System.EventArgs e)
0x24efc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x24f01  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x24f06  dup
0x24f07  ldarg.0
0x24f08  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::noBtn
0x24f0d  ldstr    aNobtn// "noBtn"
0x24f12  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24f17  ldarg.0
0x24f18  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::noBtn
0x24f1d  ldc.i4.2
0x24f1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x24f23  ldarg.0
0x24f24  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::noBtn
0x24f29  ldstr    aNobtn// "noBtn"
0x24f2e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24f33  ldarg.0
0x24f34  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::noBtn
0x24f39  ldarg.0
0x24f3a  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::noBtn_Click(object sender, class [mscorlib]System.EventArgs e)
0x24f40  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x24f45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x24f4a  ldarg.0
0x24f4b  ldc.i4.3
0x24f4c  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x24f51  ldarg.0
0x24f52  ldstr    aThis// "$this"
0x24f57  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x24f5c  ldarg.0
0x24f5d  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x24f62  ldarg.0
0x24f63  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24f68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x24f6d  ldarg.0
0x24f6e  ldc.i4.3
0x24f6f  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_FormBorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FormBorderStyle)
0x24f74  ldarg.0
0x24f75  ldc.i4.0
0x24f76  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MaximizeBox(bool)
0x24f7b  ldarg.0
0x24f7c  ldc.i4.0
0x24f7d  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_MinimizeBox(bool)
0x24f82  ldarg.0
0x24f83  ldstr    aEventhelpandsu_1// "EventHelpAndSupportConfirmDlg"
0x24f88  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x24f8d  ldarg.0
0x24f8e  ldc.i4.0
0x24f8f  call     instance void [System.Windows.Forms]System.Windows.Forms.Form::set_ShowInTaskbar(bool)
0x24f94  ldarg.0
0x24f95  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24f9a  ldc.i4.0
0x24f9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x24fa0  ldarg.0
0x24fa1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::tableLayoutPanel
0x24fa6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x24fab  ldarg.0
0x24fac  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24fb1  ldc.i4.0
0x24fb2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x24fb7  ldarg.0
0x24fb8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.EventHelpAndSupportConfirmDlg::buttonLayoutPanel
0x24fbd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x24fc2  ldarg.0
0x24fc3  ldc.i4.0
0x24fc4  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x24fc9  ret
```
