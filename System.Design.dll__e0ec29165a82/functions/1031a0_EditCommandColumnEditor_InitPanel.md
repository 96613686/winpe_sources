# EditCommandColumnEditor::InitPanel

- ea: `0x1031a0`
- end: `0x103483`
- name: `EditCommandColumnEditor::InitPanel`
- size: `739`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x8ef40`

## string_xrefs

- `0x103275`: `DGCol_EC_Update`
- `0x103293`: `EditColumnUpdateTextLabel`
- `0x1032db`: `EditColumnUpdateTextEdit`
- `0x1033e2`: `DGCol_EC_BT_Link`
- `0x103428`: `EditColumnButtonTypeCombo`

## pseudocode

```c

```

## disassembly

```asm
0x1031a0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1031a5  stloc.0
0x1031a6  ldarg.0
0x1031a7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1031ac  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::editTextEdit
0x1031b1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1031b6  stloc.1
0x1031b7  ldarg.0
0x1031b8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1031bd  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::updateTextEdit
0x1031c2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1031c7  stloc.2
0x1031c8  ldarg.0
0x1031c9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1031ce  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::cancelTextEdit
0x1031d3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1031d8  stloc.3
0x1031d9  ldarg.0
0x1031da  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x1031df  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox EditCommandColumnEditor::buttonTypeCombo
0x1031e4  ldloc.0
0x1031e5  ldc.i4.0
0x1031e6  ldc.i4.0
0x1031e7  ldc.i4   0xA0
0x1031ec  ldc.i4.s 0xE
0x1031ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1031f3  ldloc.0
0x1031f4  ldstr    aDgcolEcEdit// "DGCol_EC_Edit"
0x1031f9  call     string System.Design.SR::GetString(string name)
0x1031fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x103203  ldloc.0
0x103204  ldc.i4.0
0x103205  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x10320a  ldloc.0
0x10320b  ldc.i4.1
0x10320c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x103211  ldloc.0
0x103212  ldstr    aEditcolumnedit// "EditColumnEditTextLabel"
0x103217  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x10321c  ldarg.0
0x10321d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::editTextEdit
0x103222  ldc.i4.0
0x103223  ldc.i4.s 0x10
0x103225  ldc.i4   0xB6
0x10322a  ldc.i4.s 0x18
0x10322c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x103231  ldarg.0
0x103232  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::editTextEdit
0x103237  ldc.i4.2
0x103238  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x10323d  ldarg.0
0x10323e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::editTextEdit
0x103243  ldarg.0
0x103244  ldftn    instance void EditCommandColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x10324a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x10324f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x103254  ldarg.0
0x103255  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::editTextEdit
0x10325a  ldstr    aEditcolumnedit_0// "EditColumnEditTextEdit"
0x10325f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x103264  ldloc.1
0x103265  ldc.i4.0
0x103266  ldc.i4.s 0x28
0x103268  ldc.i4   0xA0
0x10326d  ldc.i4.s 0xE
0x10326f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x103274  ldloc.1
0x103275  ldstr    aDgcolEcUpdate// "DGCol_EC_Update"
0x10327a  call     string System.Design.SR::GetString(string name)
0x10327f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x103284  ldloc.1
0x103285  ldc.i4.0
0x103286  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x10328b  ldloc.1
0x10328c  ldc.i4.3
0x10328d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x103292  ldloc.1
0x103293  ldstr    aEditcolumnupda// "EditColumnUpdateTextLabel"
0x103298  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x10329d  ldarg.0
0x10329e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::updateTextEdit
0x1032a3  ldc.i4.0
0x1032a4  ldc.i4.s 0x38
0x1032a6  ldc.i4   0xB6
0x1032ab  ldc.i4.s 0x18
0x1032ad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1032b2  ldarg.0
0x1032b3  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::updateTextEdit
0x1032b8  ldc.i4.4
0x1032b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1032be  ldarg.0
0x1032bf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::updateTextEdit
0x1032c4  ldarg.0
0x1032c5  ldftn    instance void EditCommandColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x1032cb  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1032d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x1032d5  ldarg.0
0x1032d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::updateTextEdit
0x1032db  ldstr    aEditcolumnupda_0// "EditColumnUpdateTextEdit"
0x1032e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1032e5  ldloc.2
0x1032e6  ldc.i4   0xC8
0x1032eb  ldc.i4.0
0x1032ec  ldc.i4   0xA0
0x1032f1  ldc.i4.s 0xE
0x1032f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1032f8  ldloc.2
0x1032f9  ldstr    aDgcolEcCancel// "DGCol_EC_Cancel"
0x1032fe  call     string System.Design.SR::GetString(string name)
0x103303  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x103308  ldloc.2
0x103309  ldc.i4.0
0x10330a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x10330f  ldloc.2
0x103310  ldc.i4.5
0x103311  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x103316  ldloc.2
0x103317  ldstr    aEditcolumncanc// "EditColumnCancelTextLabel"
0x10331c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x103321  ldarg.0
0x103322  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::cancelTextEdit
0x103327  ldc.i4   0xC8
0x10332c  ldc.i4.s 0x10
0x10332e  ldc.i4   0xB6
0x103333  ldc.i4.s 0x18
0x103335  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x10333a  ldarg.0
0x10333b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::cancelTextEdit
0x103340  ldc.i4.6
0x103341  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x103346  ldarg.0
0x103347  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::cancelTextEdit
0x10334c  ldarg.0
0x10334d  ldftn    instance void EditCommandColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x103353  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x103358  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x10335d  ldarg.0
0x10335e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::cancelTextEdit
0x103363  ldstr    aEditcolumncanc_0// "EditColumnCancelTextEdit"
0x103368  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x10336d  ldloc.3
0x10336e  ldc.i4   0xC8
0x103373  ldc.i4.s 0x28
0x103375  ldc.i4   0xA0
0x10337a  ldc.i4.s 0xE
0x10337c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x103381  ldloc.3
0x103382  ldstr    aDgcolEcButtont// "DGCol_EC_ButtonType"
0x103387  call     string System.Design.SR::GetString(string name)
0x10338c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x103391  ldloc.3
0x103392  ldc.i4.0
0x103393  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x103398  ldloc.3
0x103399  ldc.i4.7
0x10339a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x10339f  ldloc.3
0x1033a0  ldstr    aEditcolumnbutt// "EditColumnButtonTypeLabel"
0x1033a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1033aa  ldarg.0
0x1033ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox EditCommandColumnEditor::buttonTypeCombo
0x1033b0  ldc.i4   0xC8
0x1033b5  ldc.i4.s 0x38
0x1033b7  ldc.i4   0xB6
0x1033bc  ldc.i4.s 0x15
0x1033be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1033c3  ldarg.0
0x1033c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox EditCommandColumnEditor::buttonTypeCombo
0x1033c9  ldc.i4.2
0x1033ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x1033cf  ldarg.0
0x1033d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox EditCommandColumnEditor::buttonTypeCombo
0x1033d5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x1033da  ldc.i4.2
0x1033db  newarr   [mscorlib]System.Object
0x1033e0  dup
0x1033e1  ldc.i4.0
0x1033e2  ldstr    aDgcolEcBtLink// "DGCol_EC_BT_Link"
0x1033e7  call     string System.Design.SR::GetString(string name)
0x1033ec  stelem.ref
0x1033ed  dup
0x1033ee  ldc.i4.1
0x1033ef  ldstr    aDgcolEcBtPush// "DGCol_EC_BT_Push"
0x1033f4  call     string System.Design.SR::GetString(string name)
0x1033f9  stelem.ref
0x1033fa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::AddRange(object[])
0x1033ff  ldarg.0
0x103400  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox EditCommandColumnEditor::buttonTypeCombo
0x103405  ldc.i4.8
0x103406  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x10340b  ldarg.0
0x10340c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox EditCommandColumnEditor::buttonTypeCombo
0x103411  ldarg.0
0x103412  ldftn    instance void EditCommandColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x103418  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x10341d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x103422  ldarg.0
0x103423  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox EditCommandColumnEditor::buttonTypeCombo
0x103428  ldstr    aEditcolumnbutt_0// "EditColumnButtonTypeCombo"
0x10342d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x103432  ldarg.0
0x103433  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x103438  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Clear()
0x10343d  ldarg.0
0x10343e  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x103443  ldc.i4.8
0x103444  newarr   [System.Windows.Forms]System.Windows.Forms.Control
0x103449  dup
0x10344a  ldc.i4.0
0x10344b  ldarg.0
0x10344c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox EditCommandColumnEditor::buttonTypeCombo
0x103451  stelem.ref
0x103452  dup
0x103453  ldc.i4.1
0x103454  ldloc.3
0x103455  stelem.ref
0x103456  dup
0x103457  ldc.i4.2
0x103458  ldarg.0
0x103459  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::cancelTextEdit
0x10345e  stelem.ref
0x10345f  dup
0x103460  ldc.i4.3
0x103461  ldloc.2
0x103462  stelem.ref
0x103463  dup
0x103464  ldc.i4.4
0x103465  ldarg.0
0x103466  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::updateTextEdit
0x10346b  stelem.ref
0x10346c  dup
0x10346d  ldc.i4.5
0x10346e  ldloc.1
0x10346f  stelem.ref
0x103470  dup
0x103471  ldc.i4.6
0x103472  ldarg.0
0x103473  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox EditCommandColumnEditor::editTextEdit
0x103478  stelem.ref
0x103479  dup
0x10347a  ldc.i4.7
0x10347b  ldloc.0
0x10347c  stelem.ref
0x10347d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.Control[])
0x103482  ret
```
