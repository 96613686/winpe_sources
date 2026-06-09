# Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::InitializeComponent

- ea: `0x16cb0`
- end: `0x1722d`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::InitializeComponent`
- size: `1405`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x16980`

## string_xrefs

- `0x16f42`: `removeButton`
- `0x16f52`: `removeButton`
- `0x16fea`: `buttonMoveDown`
- `0x16ffa`: `buttonMoveDown`
- `0x171f0`: `AddRemoveColumnsDialog`

## pseudocode

```c

```

## disassembly

```asm
0x16cb0  ldtoken  Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog
0x16cb5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16cba  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x16cbf  ldarg.0
0x16cc0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x16cc5  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonOK
0x16cca  ldarg.0
0x16ccb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x16cd0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonCancel
0x16cd5  ldarg.0
0x16cd6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x16cdb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::label1
0x16ce0  ldarg.0
0x16ce1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x16ce6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::label2
0x16ceb  ldarg.0
0x16cec  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListBox::.ctor()
0x16cf1  stfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x16cf6  ldarg.0
0x16cf7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListBox::.ctor()
0x16cfc  stfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x16d01  ldarg.0
0x16d02  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x16d07  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::addButton
0x16d0c  ldarg.0
0x16d0d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x16d12  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::removeButton
0x16d17  ldarg.0
0x16d18  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x16d1d  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::restoreButton
0x16d22  ldarg.0
0x16d23  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x16d28  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::upButton
0x16d2d  ldarg.0
0x16d2e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x16d33  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonMoveDown
0x16d38  ldarg.0
0x16d39  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x16d3e  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::groupBoxLine
0x16d43  ldarg.0
0x16d44  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x16d49  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x16d4e  ldarg.0
0x16d4f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x16d54  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x16d59  ldarg.0
0x16d5a  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x16d5f  dup
0x16d60  ldarg.0
0x16d61  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonOK
0x16d66  ldstr    aButtonok// "buttonOK"
0x16d6b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16d70  ldarg.0
0x16d71  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonOK
0x16d76  ldc.i4.1
0x16d77  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x16d7c  ldarg.0
0x16d7d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonOK
0x16d82  ldstr    aButtonok// "buttonOK"
0x16d87  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16d8c  dup
0x16d8d  ldarg.0
0x16d8e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonCancel
0x16d93  ldstr    aButtoncancel// "buttonCancel"
0x16d98  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16d9d  ldarg.0
0x16d9e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonCancel
0x16da3  ldc.i4.2
0x16da4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x16da9  ldarg.0
0x16daa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonCancel
0x16daf  ldstr    aButtoncancel// "buttonCancel"
0x16db4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16db9  dup
0x16dba  ldarg.0
0x16dbb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::label1
0x16dc0  ldstr    aLabel1// "label1"
0x16dc5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16dca  ldarg.0
0x16dcb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::label1
0x16dd0  ldstr    aLabel1// "label1"
0x16dd5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16dda  dup
0x16ddb  ldarg.0
0x16ddc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::label2
0x16de1  ldstr    aLabel2// "label2"
0x16de6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16deb  ldarg.0
0x16dec  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::label2
0x16df1  ldstr    aLabel2// "label2"
0x16df6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16dfb  dup
0x16dfc  ldarg.0
0x16dfd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x16e02  ldstr    aListboxavailab// "listBoxAvailableColumns"
0x16e07  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16e0c  ldarg.0
0x16e0d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x16e12  ldc.i4.1
0x16e13  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x16e18  ldarg.0
0x16e19  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x16e1e  ldstr    aListboxavailab// "listBoxAvailableColumns"
0x16e23  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16e28  ldarg.0
0x16e29  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x16e2e  ldarg.0
0x16e2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x16e34  ldc.i4.5
0x16e35  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x16e3a  ldarg.0
0x16e3b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x16e40  ldarg.0
0x16e41  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x16e47  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16e4c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x16e51  ldarg.0
0x16e52  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x16e57  ldarg.0
0x16e58  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns_Entered(object sender, class [mscorlib]System.EventArgs e)
0x16e5e  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16e63  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Enter(class [mscorlib]System.EventHandler)
0x16e68  ldarg.0
0x16e69  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x16e6e  ldarg.0
0x16e6f  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns_DoubleClick(object sender, class [mscorlib]System.EventArgs e)
0x16e75  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16e7a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_DoubleClick(class [mscorlib]System.EventHandler)
0x16e7f  dup
0x16e80  ldarg.0
0x16e81  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x16e86  ldstr    aListboxselecte// "listBoxSelectedColumns"
0x16e8b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16e90  ldarg.0
0x16e91  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x16e96  ldc.i4.1
0x16e97  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListControl::set_FormattingEnabled(bool)
0x16e9c  ldarg.0
0x16e9d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x16ea2  ldstr    aListboxselecte// "listBoxSelectedColumns"
0x16ea7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16eac  ldarg.0
0x16ead  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x16eb2  ldarg.0
0x16eb3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x16eb8  ldc.i4.5
0x16eb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x16ebe  ldarg.0
0x16ebf  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x16ec4  ldarg.0
0x16ec5  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x16ecb  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16ed0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x16ed5  ldarg.0
0x16ed6  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x16edb  ldarg.0
0x16edc  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns_Entered(object sender, class [mscorlib]System.EventArgs e)
0x16ee2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16ee7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Enter(class [mscorlib]System.EventHandler)
0x16eec  ldarg.0
0x16eed  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x16ef2  ldarg.0
0x16ef3  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns_DoubleClick(object sender, class [mscorlib]System.EventArgs e)
0x16ef9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16efe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_DoubleClick(class [mscorlib]System.EventHandler)
0x16f03  dup
0x16f04  ldarg.0
0x16f05  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::addButton
0x16f0a  ldstr    aAddbutton// "addButton"
0x16f0f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16f14  ldarg.0
0x16f15  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::addButton
0x16f1a  ldstr    aAddbutton// "addButton"
0x16f1f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16f24  ldarg.0
0x16f25  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::addButton
0x16f2a  ldarg.0
0x16f2b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::addButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x16f31  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16f36  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x16f3b  dup
0x16f3c  ldarg.0
0x16f3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::removeButton
0x16f42  ldstr    aRemovebutton// "removeButton"
0x16f47  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16f4c  ldarg.0
0x16f4d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::removeButton
0x16f52  ldstr    aRemovebutton// "removeButton"
0x16f57  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16f5c  ldarg.0
0x16f5d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::removeButton
0x16f62  ldarg.0
0x16f63  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::removeButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x16f69  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16f6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x16f73  dup
0x16f74  ldarg.0
0x16f75  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::restoreButton
0x16f7a  ldstr    aRestorebutton// "restoreButton"
0x16f7f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16f84  ldarg.0
0x16f85  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::restoreButton
0x16f8a  ldstr    aRestorebutton// "restoreButton"
0x16f8f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16f94  ldarg.0
0x16f95  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::restoreButton
0x16f9a  ldarg.0
0x16f9b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::restoreButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x16fa1  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16fa6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x16fab  dup
0x16fac  ldarg.0
0x16fad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::upButton
0x16fb2  ldstr    aUpbutton// "upButton"
0x16fb7  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16fbc  ldarg.0
0x16fbd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::upButton
0x16fc2  ldstr    aUpbutton// "upButton"
0x16fc7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x16fcc  ldarg.0
0x16fcd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::upButton
0x16fd2  ldarg.0
0x16fd3  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::upButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x16fd9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x16fde  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x16fe3  dup
0x16fe4  ldarg.0
0x16fe5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonMoveDown
0x16fea  ldstr    aButtonmovedown// "buttonMoveDown"
0x16fef  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x16ff4  ldarg.0
0x16ff5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonMoveDown
0x16ffa  ldstr    aButtonmovedown// "buttonMoveDown"
0x16fff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x17004  ldarg.0
0x17005  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonMoveDown
0x1700a  ldarg.0
0x1700b  ldftn    instance void Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonMoveDown_Click(object sender, class [mscorlib]System.EventArgs e)
0x17011  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x17016  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x1701b  ldarg.0
0x1701c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x17021  ldarg.0
0x17022  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::groupBoxLine
0x17027  ldc.i4.4
0x17028  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0x1702d  dup
0x1702e  ldarg.0
0x1702f  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::groupBoxLine
0x17034  ldstr    aGroupboxline// "groupBoxLine"
0x17039  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1703e  ldarg.0
0x1703f  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::groupBoxLine
0x17044  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ButtonShadow()
0x17049  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0x1704e  ldarg.0
0x1704f  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::groupBoxLine
0x17054  ldstr    aGroupboxline// "groupBoxLine"
0x17059  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1705e  ldarg.0
0x1705f  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::groupBoxLine
0x17064  ldc.i4.0
0x17065  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x1706a  dup
0x1706b  ldarg.0
0x1706c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x17071  ldstr    aTablelayoutpan_0// "tableLayoutPanel"
0x17076  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1707b  ldarg.0
0x1707c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x17081  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x17086  ldarg.0
0x17087  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::buttonCancel
0x1708c  ldc.i4.3
0x1708d  ldc.i4.7
0x1708e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x17093  ldarg.0
0x17094  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x17099  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1709e  ldarg.0
0x1709f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxSelectedColumns
0x170a4  ldc.i4.2
0x170a5  ldc.i4.1
0x170a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x170ab  ldarg.0
0x170ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x170b1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x170b6  ldarg.0
0x170b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::upButton
0x170bc  ldc.i4.3
0x170bd  ldc.i4.2
0x170be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x170c3  ldarg.0
0x170c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::tableLayoutPanel
0x170c9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x170ce  ldarg.0
0x170cf  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox Microsoft.Windows.ManagementUI.CombinedControls.AddRemoveColumnsDialog::listBoxAvailableColumns
0x170d4  ldc.i4.0
0x170d5  ldc.i4.1
0x170d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
  ... truncated ...
```
