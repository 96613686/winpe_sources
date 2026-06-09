# System.Web.UI.Design.DataBindingsDialog::InitializeComponent

- ea: `0x7d90`
- end: `0x88d7`
- name: `System.Web.UI.Design.DataBindingsDialog::InitializeComponent`
- size: `2887`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7bb0`

## callees

- `0x51a90`

## string_xrefs

- `0x812f`: `_fieldCombo`
- `0x81de`: `_formatCombo`
- `0x8426`: `_refreshSchemaLink`

## pseudocode

```c

```

## disassembly

```asm
0x7d90  ldarg.0
0x7d91  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7d96  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_instructionLabel
0x7d9b  ldarg.0
0x7d9c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7da1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindablePropsLabels
0x7da6  ldarg.0
0x7da7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeView::.ctor()
0x7dac  stfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7db1  ldarg.0
0x7db2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7db7  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x7dbc  ldarg.0
0x7dbd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7dc2  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindingLabel
0x7dc7  ldarg.0
0x7dc8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x7dcd  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.DataBindingsDialog::_fieldBindingRadio
0x7dd2  ldarg.0
0x7dd3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7dd8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_fieldLabel
0x7ddd  ldarg.0
0x7dde  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x7de3  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.DataBindingsDialog::_fieldCombo
0x7de8  ldarg.0
0x7de9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7dee  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_formatLabel
0x7df3  ldarg.0
0x7df4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x7df9  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.DataBindingsDialog::_formatCombo
0x7dfe  ldarg.0
0x7dff  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7e04  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_sampleLabel
0x7e09  ldarg.0
0x7e0a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x7e0f  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.DataBindingsDialog::_sampleTextBox
0x7e14  ldarg.0
0x7e15  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x7e1a  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.DataBindingsDialog::_exprBindingRadio
0x7e1f  ldarg.0
0x7e20  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x7e25  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.DataBindingsDialog::_exprTextBox
0x7e2a  ldarg.0
0x7e2b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x7e30  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.DataBindingsDialog::_okButton
0x7e35  ldarg.0
0x7e36  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x7e3b  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.DataBindingsDialog::_cancelButton
0x7e40  ldarg.0
0x7e41  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x7e46  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel System.Web.UI.Design.DataBindingsDialog::_refreshSchemaLink
0x7e4b  ldarg.0
0x7e4c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7e51  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_exprLabel
0x7e56  ldarg.0
0x7e57  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x7e5c  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_twoWayBindingCheckBox
0x7e61  ldarg.0
0x7e62  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x7e67  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.DataBindingsDialog::_fieldBindingPanel
0x7e6c  ldarg.0
0x7e6d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x7e72  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.DataBindingsDialog::_customBindingPanel
0x7e77  ldarg.0
0x7e78  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x7e7d  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.DataBindingsDialog::_bindingOptionsPanel
0x7e82  ldarg.0
0x7e83  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x7e88  ldarg.0
0x7e89  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_instructionLabel
0x7e8e  ldc.i4.3
0x7e8f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x7e94  ldarg.0
0x7e95  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_instructionLabel
0x7e9a  ldc.i4.s 0xC
0x7e9c  ldc.i4.s 0xC
0x7e9e  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x7ea3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7ea8  ldarg.0
0x7ea9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_instructionLabel
0x7eae  ldstr    aInstructionlab// "_instructionLabel"
0x7eb3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7eb8  ldarg.0
0x7eb9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_instructionLabel
0x7ebe  ldc.i4   0x1FC
0x7ec3  ldc.i4.s 0x1E
0x7ec5  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x7eca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x7ecf  ldarg.0
0x7ed0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_instructionLabel
0x7ed5  ldc.i4.0
0x7ed6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x7edb  ldarg.0
0x7edc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindablePropsLabels
0x7ee1  ldc.i4.3
0x7ee2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x7ee7  ldarg.0
0x7ee8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindablePropsLabels
0x7eed  ldc.i4.s 0xC
0x7eef  ldc.i4.s 0x34
0x7ef1  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x7ef6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7efb  ldarg.0
0x7efc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindablePropsLabels
0x7f01  ldstr    aBindablepropsl// "_bindablePropsLabels"
0x7f06  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7f0b  ldarg.0
0x7f0c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindablePropsLabels
0x7f11  ldc.i4   0xB8
0x7f16  ldc.i4.s 0x10
0x7f18  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x7f1d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x7f22  ldarg.0
0x7f23  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindablePropsLabels
0x7f28  ldc.i4.1
0x7f29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x7f2e  ldarg.0
0x7f2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7f34  ldc.i4.0
0x7f35  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_HideSelection(bool)
0x7f3a  ldarg.0
0x7f3b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7f40  ldc.i4.m1
0x7f41  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ImageIndex(int32)
0x7f46  ldarg.0
0x7f47  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7f4c  ldc.i4.s 0xC
0x7f4e  ldc.i4.s 0x48
0x7f50  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x7f55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7f5a  ldarg.0
0x7f5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7f60  ldstr    aBindablepropst// "_bindablePropsTree"
0x7f65  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7f6a  ldarg.0
0x7f6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7f70  ldc.i4.m1
0x7f71  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_SelectedImageIndex(int32)
0x7f76  ldarg.0
0x7f77  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7f7c  ldc.i4.0
0x7f7d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ShowLines(bool)
0x7f82  ldarg.0
0x7f83  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7f88  ldc.i4.0
0x7f89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ShowPlusMinus(bool)
0x7f8e  ldarg.0
0x7f8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7f94  ldc.i4.0
0x7f95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_ShowRootLines(bool)
0x7f9a  ldarg.0
0x7f9b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7fa0  ldc.i4   0xB8
0x7fa5  ldc.i4.s 0x70
0x7fa7  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x7fac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x7fb1  ldarg.0
0x7fb2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7fb7  ldc.i4.2
0x7fb8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x7fbd  ldarg.0
0x7fbe  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7fc3  ldc.i4.1
0x7fc4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_Sorted(bool)
0x7fc9  ldarg.0
0x7fca  ldfld    class [System.Windows.Forms]System.Windows.Forms.TreeView System.Web.UI.Design.DataBindingsDialog::_bindablePropsTree
0x7fcf  ldarg.0
0x7fd0  ldftn    instance void System.Web.UI.Design.DataBindingsDialog::OnBindablePropsTreeAfterSelect(object sender, class [System.Windows.Forms]System.Windows.Forms.TreeViewEventArgs e)
0x7fd6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler::.ctor(object, native int)
0x7fdb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_AfterSelect(class [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler)
0x7fe0  ldarg.0
0x7fe1  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x7fe6  ldc.i4.3
0x7fe7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x7fec  ldarg.0
0x7fed  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x7ff2  ldc.i4.s 0xC
0x7ff4  ldc.i4   0xBE
0x7ff9  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x7ffe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x8003  ldarg.0
0x8004  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x8009  ldstr    aAllpropscheckb// "_allPropsCheckBox"
0x800e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8013  ldarg.0
0x8014  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x8019  ldc.i4   0xB8
0x801e  ldc.i4.s 0x28
0x8020  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x8025  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x802a  ldarg.0
0x802b  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x8030  ldc.i4.3
0x8031  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x8036  ldarg.0
0x8037  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x803c  ldc.i4.1
0x803d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x8042  ldarg.0
0x8043  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x8048  ldarg.0
0x8049  ldftn    instance void System.Web.UI.Design.DataBindingsDialog::OnShowAllCheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x804f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x8054  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x8059  ldarg.0
0x805a  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x805f  ldc.i4.1
0x8060  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x8065  ldarg.0
0x8066  ldfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.DataBindingsDialog::_allPropsCheckBox
0x806b  ldc.i4.1
0x806c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::set_CheckAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x8071  ldarg.0
0x8072  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindingLabel
0x8077  ldc.i4   0xD2
0x807c  ldc.i4.s 0x34
0x807e  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x8083  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x8088  ldarg.0
0x8089  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindingLabel
0x808e  ldstr    aBindinggroupla// "_bindingGroupLabel"
0x8093  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8098  ldarg.0
0x8099  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindingLabel
0x809e  ldc.i4   0x132
0x80a3  ldc.i4.s 0x10
0x80a5  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x80aa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x80af  ldarg.0
0x80b0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_bindingLabel
0x80b5  ldc.i4.4
0x80b6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x80bb  ldarg.0
0x80bc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_fieldLabel
0x80c1  ldc.i4.3
0x80c2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x80c7  ldarg.0
0x80c8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_fieldLabel
0x80cd  ldc.i4.0
0x80ce  ldc.i4.4
0x80cf  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x80d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x80d9  ldarg.0
0x80da  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_fieldLabel
0x80df  ldstr    aFieldlabel// "_fieldLabel"
0x80e4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x80e9  ldarg.0
0x80ea  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_fieldLabel
0x80ef  ldc.i4.s 0x68
0x80f1  ldc.i4.s 0x10
0x80f3  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x80f8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x80fd  ldarg.0
0x80fe  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_fieldLabel
0x8103  ldc.i4.s 0x64
0x8105  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x810a  ldarg.0
0x810b  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.DataBindingsDialog::_fieldCombo
0x8110  ldc.i4.2
0x8111  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x8116  ldarg.0
0x8117  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.DataBindingsDialog::_fieldCombo
0x811c  ldc.i4.s 0x76
0x811e  ldc.i4.0
0x811f  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x8124  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x8129  ldarg.0
0x812a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.DataBindingsDialog::_fieldCombo
0x812f  ldstr    aFieldcombo// "_fieldCombo"
0x8134  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8139  ldarg.0
0x813a  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.DataBindingsDialog::_fieldCombo
0x813f  ldc.i4   0xA4
0x8144  ldc.i4.s 0x15
0x8146  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x814b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x8150  ldarg.0
0x8151  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.DataBindingsDialog::_fieldCombo
0x8156  ldc.i4.s 0x65
0x8158  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x815d  ldarg.0
0x815e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Web.UI.Design.DataBindingsDialog::_fieldCombo
0x8163  ldarg.0
0x8164  ldftn    instance void System.Web.UI.Design.DataBindingsDialog::OnFieldComboSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x816a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x816f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x8174  ldarg.0
0x8175  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_formatLabel
0x817a  ldc.i4.3
0x817b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0x8180  ldarg.0
0x8181  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_formatLabel
0x8186  ldc.i4.0
0x8187  ldc.i4.s 0x20
0x8189  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x818e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x8193  ldarg.0
0x8194  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.DataBindingsDialog::_formatLabel
0x8199  ldstr    aFormatlabel// "_formatLabel"
0x819e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
  ... truncated ...
```
