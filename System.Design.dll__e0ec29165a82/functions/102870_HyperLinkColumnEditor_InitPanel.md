# HyperLinkColumnEditor::InitPanel

- ea: `0x102870`
- end: `0x102e4c`
- name: `HyperLinkColumnEditor::InitPanel`
- size: `1500`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x535f0`
- `0x8ef40`

## string_xrefs

- `0x10292e`: `HyperlinkColumnTextLabel`
- `0x102976`: `HyperlinkColumnTextEdit`
- `0x1029af`: `HyperlinkColumnDataTextFieldLabel`
- `0x102a03`: `HyperlinkColumnDataTextFieldCombo`
- `0x102a4b`: `HyperlinkColumnDataTextFieldEdit`
- `0x102a84`: `HyperlinkColumnDataTextFormatStringLabel`
- `0x102acc`: `HyperlinkColumnDataTextFormatStringEdit`
- `0x102b05`: `HyperlinkColumnTargetLabel`
- `0x102ba5`: `HyperlinkColumnTargetCombo`
- `0x102be7`: `HyperlinkColumnUrlLabel`
- `0x102c34`: `HyperlinkColumnUrlEdit`
- `0x102c77`: `HyperlinkColumnDataUrlFieldLabel`
- `0x102cd0`: `HyperlinkColumnDataUrlFieldCombo`
- `0x102d1d`: `HyperlinkColumnDataUrlFieldEdit`
- `0x102d60`: `HyperlinkColumnDataUrlFormatStringLabel`
- `0x102dad`: `HyperlinkColumnDataUrlFormatStringEdit`

## pseudocode

```c

```

## disassembly

```asm
0x102870  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x102875  stloc.0
0x102876  ldarg.0
0x102877  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x10287c  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::textEdit
0x102881  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x102886  stloc.1
0x102887  ldarg.0
0x102888  newobj   instance void System.Web.UI.Design.Util.UnsettableComboBox::.ctor()
0x10288d  stfld    class System.Web.UI.Design.Util.UnsettableComboBox HyperLinkColumnEditor::dataTextFieldCombo
0x102892  ldarg.0
0x102893  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x102898  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFieldEdit
0x10289d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1028a2  stloc.2
0x1028a3  ldarg.0
0x1028a4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1028a9  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFormatStringEdit
0x1028ae  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1028b3  stloc.3
0x1028b4  ldarg.0
0x1028b5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x1028ba  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkColumnEditor::targetCombo
0x1028bf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1028c4  stloc.s  4
0x1028c6  ldarg.0
0x1028c7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1028cc  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::urlEdit
0x1028d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1028d6  stloc.s  5
0x1028d8  ldarg.0
0x1028d9  newobj   instance void System.Web.UI.Design.Util.UnsettableComboBox::.ctor()
0x1028de  stfld    class System.Web.UI.Design.Util.UnsettableComboBox HyperLinkColumnEditor::dataUrlFieldCombo
0x1028e3  ldarg.0
0x1028e4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1028e9  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataUrlFieldEdit
0x1028ee  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1028f3  stloc.s  6
0x1028f5  ldarg.0
0x1028f6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1028fb  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataUrlFormatStringEdit
0x102900  ldloc.0
0x102901  ldc.i4.0
0x102902  ldc.i4.0
0x102903  ldc.i4   0xA0
0x102908  ldc.i4.s 0xE
0x10290a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x10290f  ldloc.0
0x102910  ldstr    aDgcolHcText// "DGCol_HC_Text"
0x102915  call     string System.Design.SR::GetString(string name)
0x10291a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x10291f  ldloc.0
0x102920  ldc.i4.0
0x102921  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x102926  ldloc.0
0x102927  ldc.i4.1
0x102928  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x10292d  ldloc.0
0x10292e  ldstr    aHyperlinkcolum_0// "HyperlinkColumnTextLabel"
0x102933  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102938  ldarg.0
0x102939  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::textEdit
0x10293e  ldc.i4.0
0x10293f  ldc.i4.s 0x10
0x102941  ldc.i4   0xB6
0x102946  ldc.i4.s 0x18
0x102948  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x10294d  ldarg.0
0x10294e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::textEdit
0x102953  ldc.i4.2
0x102954  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102959  ldarg.0
0x10295a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::textEdit
0x10295f  ldarg.0
0x102960  ldftn    instance void HyperLinkColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102966  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x10296b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x102970  ldarg.0
0x102971  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::textEdit
0x102976  ldstr    aHyperlinkcolum_1// "HyperlinkColumnTextEdit"
0x10297b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102980  ldloc.1
0x102981  ldc.i4.0
0x102982  ldc.i4.s 0x28
0x102984  ldc.i4   0xA0
0x102989  ldc.i4.s 0xE
0x10298b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102990  ldloc.1
0x102991  ldstr    aDgcolHcDatatex// "DGCol_HC_DataTextField"
0x102996  call     string System.Design.SR::GetString(string name)
0x10299b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1029a0  ldloc.1
0x1029a1  ldc.i4.0
0x1029a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x1029a7  ldloc.1
0x1029a8  ldc.i4.3
0x1029a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1029ae  ldloc.1
0x1029af  ldstr    aHyperlinkcolum_2// "HyperlinkColumnDataTextFieldLabel"
0x1029b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1029b9  ldarg.0
0x1029ba  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox HyperLinkColumnEditor::dataTextFieldCombo
0x1029bf  ldc.i4.0
0x1029c0  ldc.i4.s 0x38
0x1029c2  ldc.i4   0xB6
0x1029c7  ldc.i4.s 0x15
0x1029c9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1029ce  ldarg.0
0x1029cf  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox HyperLinkColumnEditor::dataTextFieldCombo
0x1029d4  ldc.i4.2
0x1029d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x1029da  ldarg.0
0x1029db  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox HyperLinkColumnEditor::dataTextFieldCombo
0x1029e0  ldc.i4.4
0x1029e1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1029e6  ldarg.0
0x1029e7  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox HyperLinkColumnEditor::dataTextFieldCombo
0x1029ec  ldarg.0
0x1029ed  ldftn    instance void HyperLinkColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x1029f3  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1029f8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x1029fd  ldarg.0
0x1029fe  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox HyperLinkColumnEditor::dataTextFieldCombo
0x102a03  ldstr    aHyperlinkcolum_3// "HyperlinkColumnDataTextFieldCombo"
0x102a08  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102a0d  ldarg.0
0x102a0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFieldEdit
0x102a13  ldc.i4.0
0x102a14  ldc.i4.s 0x38
0x102a16  ldc.i4   0xB6
0x102a1b  ldc.i4.s 0xE
0x102a1d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102a22  ldarg.0
0x102a23  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFieldEdit
0x102a28  ldc.i4.4
0x102a29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102a2e  ldarg.0
0x102a2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFieldEdit
0x102a34  ldarg.0
0x102a35  ldftn    instance void HyperLinkColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102a3b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x102a40  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x102a45  ldarg.0
0x102a46  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFieldEdit
0x102a4b  ldstr    aHyperlinkcolum_4// "HyperlinkColumnDataTextFieldEdit"
0x102a50  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102a55  ldloc.2
0x102a56  ldc.i4.0
0x102a57  ldc.i4.s 0x52
0x102a59  ldc.i4   0xA0
0x102a5e  ldc.i4.s 0xE
0x102a60  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102a65  ldloc.2
0x102a66  ldstr    aDgcolHcDatatex_0// "DGCol_HC_DataTextFormat"
0x102a6b  call     string System.Design.SR::GetString(string name)
0x102a70  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x102a75  ldloc.2
0x102a76  ldc.i4.0
0x102a77  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x102a7c  ldloc.2
0x102a7d  ldc.i4.5
0x102a7e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102a83  ldloc.2
0x102a84  ldstr    aHyperlinkcolum_5// "HyperlinkColumnDataTextFormatStringLabe"...
0x102a89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102a8e  ldarg.0
0x102a8f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFormatStringEdit
0x102a94  ldc.i4.0
0x102a95  ldc.i4.s 0x62
0x102a97  ldc.i4   0xB6
0x102a9c  ldc.i4.s 0x15
0x102a9e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102aa3  ldarg.0
0x102aa4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFormatStringEdit
0x102aa9  ldc.i4.6
0x102aaa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102aaf  ldarg.0
0x102ab0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFormatStringEdit
0x102ab5  ldarg.0
0x102ab6  ldftn    instance void HyperLinkColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102abc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x102ac1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x102ac6  ldarg.0
0x102ac7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::dataTextFormatStringEdit
0x102acc  ldstr    aHyperlinkcolum_6// "HyperlinkColumnDataTextFormatStringEdit"
0x102ad1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102ad6  ldloc.3
0x102ad7  ldc.i4.0
0x102ad8  ldc.i4.s 0x7B
0x102ada  ldc.i4   0xA0
0x102adf  ldc.i4.s 0xE
0x102ae1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102ae6  ldloc.3
0x102ae7  ldstr    aDgcolHcTarget// "DGCol_HC_Target"
0x102aec  call     string System.Design.SR::GetString(string name)
0x102af1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x102af6  ldloc.3
0x102af7  ldc.i4.0
0x102af8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x102afd  ldloc.3
0x102afe  ldc.i4.7
0x102aff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102b04  ldloc.3
0x102b05  ldstr    aHyperlinkcolum_7// "HyperlinkColumnTargetLabel"
0x102b0a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102b0f  ldarg.0
0x102b10  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkColumnEditor::targetCombo
0x102b15  ldc.i4.0
0x102b16  ldc.i4   0x8B
0x102b1b  ldc.i4   0xB6
0x102b20  ldc.i4.s 0x15
0x102b22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102b27  ldarg.0
0x102b28  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkColumnEditor::targetCombo
0x102b2d  ldc.i4.8
0x102b2e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102b33  ldarg.0
0x102b34  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkColumnEditor::targetCombo
0x102b39  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x102b3e  ldc.i4.5
0x102b3f  newarr   [mscorlib]System.Object
0x102b44  dup
0x102b45  ldc.i4.0
0x102b46  ldstr    aBlank// "_blank"
0x102b4b  stelem.ref
0x102b4c  dup
0x102b4d  ldc.i4.1
0x102b4e  ldstr    aParent_2// "_parent"
0x102b53  stelem.ref
0x102b54  dup
0x102b55  ldc.i4.2
0x102b56  ldstr    aSearch// "_search"
0x102b5b  stelem.ref
0x102b5c  dup
0x102b5d  ldc.i4.3
0x102b5e  ldstr    aSelf// "_self"
0x102b63  stelem.ref
0x102b64  dup
0x102b65  ldc.i4.4
0x102b66  ldstr    aTop_1// "_top"
0x102b6b  stelem.ref
0x102b6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::AddRange(object[])
0x102b71  ldarg.0
0x102b72  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkColumnEditor::targetCombo
0x102b77  ldarg.0
0x102b78  ldftn    instance void HyperLinkColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102b7e  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x102b83  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x102b88  ldarg.0
0x102b89  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkColumnEditor::targetCombo
0x102b8e  ldarg.0
0x102b8f  ldftn    instance void HyperLinkColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102b95  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x102b9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x102b9f  ldarg.0
0x102ba0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox HyperLinkColumnEditor::targetCombo
0x102ba5  ldstr    aHyperlinkcolum_8// "HyperlinkColumnTargetCombo"
0x102baa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102baf  ldloc.s  4
0x102bb1  ldc.i4   0xC8
0x102bb6  ldc.i4.0
0x102bb7  ldc.i4   0xA0
0x102bbc  ldc.i4.s 0xE
0x102bbe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102bc3  ldloc.s  4
0x102bc5  ldstr    aDgcolHcUrl// "DGCol_HC_URL"
0x102bca  call     string System.Design.SR::GetString(string name)
0x102bcf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x102bd4  ldloc.s  4
0x102bd6  ldc.i4.0
0x102bd7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x102bdc  ldloc.s  4
0x102bde  ldc.i4.s 0xA
0x102be0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102be5  ldloc.s  4
0x102be7  ldstr    aHyperlinkcolum_9// "HyperlinkColumnUrlLabel"
0x102bec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102bf1  ldarg.0
0x102bf2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::urlEdit
0x102bf7  ldc.i4   0xC8
0x102bfc  ldc.i4.s 0x10
0x102bfe  ldc.i4   0xB6
0x102c03  ldc.i4.s 0x18
0x102c05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102c0a  ldarg.0
0x102c0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::urlEdit
0x102c10  ldc.i4.s 0xB
0x102c12  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102c17  ldarg.0
0x102c18  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::urlEdit
0x102c1d  ldarg.0
0x102c1e  ldftn    instance void HyperLinkColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102c24  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x102c29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x102c2e  ldarg.0
0x102c2f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox HyperLinkColumnEditor::urlEdit
0x102c34  ldstr    aHyperlinkcolum_10// "HyperlinkColumnUrlEdit"
0x102c39  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102c3e  ldloc.s  5
0x102c40  ldc.i4   0xC8
  ... truncated ...
```
