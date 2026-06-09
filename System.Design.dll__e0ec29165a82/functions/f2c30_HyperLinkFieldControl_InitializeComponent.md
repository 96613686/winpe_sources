# HyperLinkFieldControl::InitializeComponent

- ea: `0xf2c30`
- end: `0xf335c`
- name: `HyperLinkFieldControl::InitializeComponent`
- size: `1836`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x8ef40`
- `0xf1df0`
- `0xf1f00`
- `0xf1f90`

## string_xrefs

- `0xf2d46`: `DCFAdd_HyperlinkText`
- `0xf3051`: `DCFAdd_HyperlinkURL`

## pseudocode

```c

```

## disassembly

```asm
0xf2c30  ldarg.0
0xf2c31  call     instance void DataControlFieldControl::InitializeComponent()
0xf2c36  ldarg.0
0xf2c37  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf2c3c  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_dataTextFieldBox
0xf2c41  ldarg.0
0xf2c42  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf2c47  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_dataNavFieldBox
0xf2c4c  ldarg.0
0xf2c4d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf2c52  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_dataNavFSBox
0xf2c57  ldarg.0
0xf2c58  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf2c5d  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_linkBox
0xf2c62  ldarg.0
0xf2c63  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf2c68  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textBox
0xf2c6d  ldarg.0
0xf2c6e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xf2c73  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textFSBox
0xf2c78  ldarg.0
0xf2c79  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0xf2c7e  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkFieldControl::_dataTextFieldList
0xf2c83  ldarg.0
0xf2c84  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0xf2c89  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkFieldControl::_dataNavFieldList
0xf2c8e  ldarg.0
0xf2c8f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0xf2c94  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_staticTextRadio
0xf2c99  ldarg.0
0xf2c9a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0xf2c9f  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_bindTextRadio
0xf2ca4  ldarg.0
0xf2ca5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0xf2caa  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_staticUrlRadio
0xf2caf  ldarg.0
0xf2cb0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0xf2cb5  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_bindUrlRadio
0xf2cba  ldarg.0
0xf2cbb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf2cc0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringLabel
0xf2cc5  ldarg.0
0xf2cc6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf2ccb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkUrlFormatStringLabel
0xf2cd0  ldarg.0
0xf2cd1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf2cd6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringExampleLabel
0xf2cdb  ldarg.0
0xf2cdc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xf2ce1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkUrlFormatStringExampleLabel
0xf2ce6  ldarg.0
0xf2ce7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0xf2cec  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox HyperLinkFieldControl::_textGroupBox
0xf2cf1  ldarg.0
0xf2cf2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0xf2cf7  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox HyperLinkFieldControl::_linkGroupBox
0xf2cfc  ldarg.0
0xf2cfd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0xf2d02  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_staticTextPanel
0xf2d07  ldarg.0
0xf2d08  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0xf2d0d  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_bindTextPanel
0xf2d12  ldarg.0
0xf2d13  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0xf2d18  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_staticUrlPanel
0xf2d1d  ldarg.0
0xf2d1e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0xf2d23  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_bindUrlPanel
0xf2d28  ldarg.0
0xf2d29  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox HyperLinkFieldControl::_textGroupBox
0xf2d2e  ldc.i4.0
0xf2d2f  ldc.i4.s 0x2F
0xf2d31  ldc.i4   0x122
0xf2d36  ldc.i4   0xA9
0xf2d3b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2d40  ldarg.0
0xf2d41  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox HyperLinkFieldControl::_textGroupBox
0xf2d46  ldstr    aDcfaddHyperlin// "DCFAdd_HyperlinkText"
0xf2d4b  call     string System.Design.SR::GetString(string name)
0xf2d50  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf2d55  ldarg.0
0xf2d56  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox HyperLinkFieldControl::_textGroupBox
0xf2d5b  ldc.i4.1
0xf2d5c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2d61  ldarg.0
0xf2d62  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_staticTextRadio
0xf2d67  ldc.i4.0
0xf2d68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2d6d  ldarg.0
0xf2d6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_staticTextRadio
0xf2d73  ldstr    aDcfaddSpecifyt// "DCFAdd_SpecifyText"
0xf2d78  call     string System.Design.SR::GetString(string name)
0xf2d7d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf2d82  ldarg.0
0xf2d83  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_staticTextRadio
0xf2d88  ldarg.0
0xf2d89  ldftn    instance void HyperLinkFieldControl::OnTextRadioChanged(object sender, class [mscorlib]System.EventArgs e)
0xf2d8f  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xf2d94  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0xf2d99  ldarg.0
0xf2d9a  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_staticTextRadio
0xf2d9f  ldc.i4.1
0xf2da0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0xf2da5  ldarg.0
0xf2da6  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_staticTextRadio
0xf2dab  ldc.i4.s 9
0xf2dad  ldc.i4.s 0x13
0xf2daf  ldc.i4   0x105
0xf2db4  ldc.i4.s 0x14
0xf2db6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2dbb  ldarg.0
0xf2dbc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textBox
0xf2dc1  ldc.i4.0
0xf2dc2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2dc7  ldarg.0
0xf2dc8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textBox
0xf2dcd  ldc.i4.0
0xf2dce  ldc.i4.0
0xf2dcf  ldc.i4   0xF6
0xf2dd4  ldc.i4.s 0x14
0xf2dd6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2ddb  ldarg.0
0xf2ddc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textBox
0xf2de1  ldarg.0
0xf2de2  ldstr    aDcfaddSpecifyt// "DCFAdd_SpecifyText"
0xf2de7  call     string System.Design.SR::GetString(string name)
0xf2dec  call     instance string DataControlFieldControl::StripAccelerators(string text)
0xf2df1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xf2df6  ldarg.0
0xf2df7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_staticTextPanel
0xf2dfc  ldc.i4.1
0xf2dfd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2e02  ldarg.0
0xf2e03  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_staticTextPanel
0xf2e08  ldc.i4.s 0x18
0xf2e0a  ldc.i4.s 0x27
0xf2e0c  ldc.i4   0xF6
0xf2e11  ldc.i4.s 0x18
0xf2e13  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2e18  ldarg.0
0xf2e19  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_staticTextPanel
0xf2e1e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xf2e23  ldarg.0
0xf2e24  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textBox
0xf2e29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xf2e2e  ldarg.0
0xf2e2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_bindTextRadio
0xf2e34  ldc.i4.2
0xf2e35  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2e3a  ldarg.0
0xf2e3b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_bindTextRadio
0xf2e40  ldstr    aDcfaddBindtext// "DCFAdd_BindText"
0xf2e45  call     string System.Design.SR::GetString(string name)
0xf2e4a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf2e4f  ldarg.0
0xf2e50  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_bindTextRadio
0xf2e55  ldc.i4.s 9
0xf2e57  ldc.i4.s 0x3F
0xf2e59  ldc.i4   0x105
0xf2e5e  ldc.i4.s 0x14
0xf2e60  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2e65  ldarg.0
0xf2e66  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkFieldControl::_dataTextFieldList
0xf2e6b  ldc.i4.0
0xf2e6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2e71  ldarg.0
0xf2e72  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkFieldControl::_dataTextFieldList
0xf2e77  ldc.i4.0
0xf2e78  ldc.i4.0
0xf2e79  ldc.i4   0xF6
0xf2e7e  ldc.i4.s 0x14
0xf2e80  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2e85  ldarg.0
0xf2e86  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkFieldControl::_dataTextFieldList
0xf2e8b  ldarg.0
0xf2e8c  ldstr    aDcfaddBindtext// "DCFAdd_BindText"
0xf2e91  call     string System.Design.SR::GetString(string name)
0xf2e96  call     instance string DataControlFieldControl::StripAccelerators(string text)
0xf2e9b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xf2ea0  ldarg.0
0xf2ea1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_dataTextFieldBox
0xf2ea6  ldc.i4.1
0xf2ea7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2eac  ldarg.0
0xf2ead  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_dataTextFieldBox
0xf2eb2  ldc.i4.0
0xf2eb3  ldc.i4.0
0xf2eb4  ldc.i4   0xF6
0xf2eb9  ldc.i4.s 0x14
0xf2ebb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2ec0  ldarg.0
0xf2ec1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_dataTextFieldBox
0xf2ec6  ldarg.0
0xf2ec7  ldstr    aDcfaddBindtext// "DCFAdd_BindText"
0xf2ecc  call     string System.Design.SR::GetString(string name)
0xf2ed1  call     instance string DataControlFieldControl::StripAccelerators(string text)
0xf2ed6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xf2edb  ldarg.0
0xf2edc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringLabel
0xf2ee1  ldstr    aDcfaddTextform// "DCFAdd_TextFormatString"
0xf2ee6  call     string System.Design.SR::GetString(string name)
0xf2eeb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf2ef0  ldarg.0
0xf2ef1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringLabel
0xf2ef6  ldc.i4.2
0xf2ef7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2efc  ldarg.0
0xf2efd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringLabel
0xf2f02  ldc.i4   0x100
0xf2f07  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf2f0c  ldarg.0
0xf2f0d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringLabel
0xf2f12  ldc.i4.0
0xf2f13  ldc.i4.s 0x14
0xf2f15  ldc.i4   0xF6
0xf2f1a  ldc.i4.s 0x11
0xf2f1c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2f21  ldarg.0
0xf2f22  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textFSBox
0xf2f27  ldc.i4.3
0xf2f28  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2f2d  ldarg.0
0xf2f2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textFSBox
0xf2f33  ldc.i4.0
0xf2f34  ldc.i4.s 0x27
0xf2f36  ldc.i4   0xF6
0xf2f3b  ldc.i4.s 0x14
0xf2f3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2f42  ldarg.0
0xf2f43  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringExampleLabel
0xf2f48  ldstr    aDcfaddTextform_0// "DCFAdd_TextFormatStringExample"
0xf2f4d  call     string System.Design.SR::GetString(string name)
0xf2f52  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xf2f57  ldarg.0
0xf2f58  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringExampleLabel
0xf2f5d  ldc.i4.0
0xf2f5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xf2f63  ldarg.0
0xf2f64  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringExampleLabel
0xf2f69  ldc.i4   0x100
0xf2f6e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xf2f73  ldarg.0
0xf2f74  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringExampleLabel
0xf2f79  ldc.i4.0
0xf2f7a  ldc.i4.s 0x3B
0xf2f7c  ldc.i4   0xF6
0xf2f81  ldc.i4.s 0x11
0xf2f83  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2f88  ldarg.0
0xf2f89  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_bindTextPanel
0xf2f8e  ldc.i4.3
0xf2f8f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xf2f94  ldarg.0
0xf2f95  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_bindTextPanel
0xf2f9a  ldc.i4.s 0x18
0xf2f9c  ldc.i4.s 0x53
0xf2f9e  ldc.i4   0xF6
0xf2fa3  ldc.i4.s 0x4E
0xf2fa5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0xf2faa  ldarg.0
0xf2fab  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel HyperLinkFieldControl::_bindTextPanel
0xf2fb0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xf2fb5  ldc.i4.6
0xf2fb6  newarr   [System.Windows.Forms]System.Windows.Forms.Control
0xf2fbb  dup
0xf2fbc  ldc.i4.0
0xf2fbd  ldarg.0
0xf2fbe  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton HyperLinkFieldControl::_bindTextRadio
0xf2fc3  stelem.ref
0xf2fc4  dup
0xf2fc5  ldc.i4.1
0xf2fc6  ldarg.0
0xf2fc7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkFieldControl::_dataTextFieldList
0xf2fcc  stelem.ref
0xf2fcd  dup
0xf2fce  ldc.i4.2
0xf2fcf  ldarg.0
0xf2fd0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_dataTextFieldBox
0xf2fd5  stelem.ref
0xf2fd6  dup
0xf2fd7  ldc.i4.3
0xf2fd8  ldarg.0
0xf2fd9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringLabel
0xf2fde  stelem.ref
0xf2fdf  dup
0xf2fe0  ldc.i4.4
0xf2fe1  ldarg.0
0xf2fe2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkFieldControl::_textFSBox
0xf2fe7  stelem.ref
0xf2fe8  dup
0xf2fe9  ldc.i4.5
0xf2fea  ldarg.0
0xf2feb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label HyperLinkFieldControl::_linkTextFormatStringExampleLabel
0xf2ff0  stelem.ref
0xf2ff1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.Control[])
0xf2ff6  ldarg.0
0xf2ff7  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox HyperLinkFieldControl::_textGroupBox
0xf2ffc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xf3001  ldc.i4.4
0xf3002  newarr   [System.Windows.Forms]System.Windows.Forms.Control
  ... truncated ...
```
