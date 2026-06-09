# ButtonColumnEditor::InitPanel

- ea: `0x1021c0`
- end: `0x1025b7`
- name: `ButtonColumnEditor::InitPanel`
- size: `1015`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x535f0`
- `0x8ef40`

## string_xrefs

- `0x102324`: `ButtonColumnDataTextFieldCombo`
- `0x10240b`: `DGCol_BC_Command`
- `0x102429`: `ButtonColumnCommandLabel`
- `0x102476`: `ButtonColumnCommandEdit`
- `0x1024fb`: `DGCol_BC_BT_Link`
- `0x102542`: `ButtonColumnButtonTypeCombo`

## pseudocode

```c

```

## disassembly

```asm
0x1021c0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1021c5  stloc.0
0x1021c6  ldarg.0
0x1021c7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1021cc  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::textEdit
0x1021d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1021d6  stloc.1
0x1021d7  ldarg.0
0x1021d8  newobj   instance void System.Web.UI.Design.Util.UnsettableComboBox::.ctor()
0x1021dd  stfld    class System.Web.UI.Design.Util.UnsettableComboBox ButtonColumnEditor::dataTextFieldCombo
0x1021e2  ldarg.0
0x1021e3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1021e8  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFieldEdit
0x1021ed  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1021f2  stloc.2
0x1021f3  ldarg.0
0x1021f4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x1021f9  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFormatStringEdit
0x1021fe  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x102203  stloc.3
0x102204  ldarg.0
0x102205  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x10220a  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::commandEdit
0x10220f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x102214  stloc.s  4
0x102216  ldarg.0
0x102217  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x10221c  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonColumnEditor::buttonTypeCombo
0x102221  ldloc.0
0x102222  ldc.i4.0
0x102223  ldc.i4.0
0x102224  ldc.i4   0xA0
0x102229  ldc.i4.s 0xE
0x10222b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102230  ldloc.0
0x102231  ldstr    aDgcolBcText// "DGCol_BC_Text"
0x102236  call     string System.Design.SR::GetString(string name)
0x10223b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x102240  ldloc.0
0x102241  ldc.i4.0
0x102242  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x102247  ldloc.0
0x102248  ldc.i4.1
0x102249  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x10224e  ldloc.0
0x10224f  ldstr    aButtoncolumnte// "ButtonColumnTextLabel"
0x102254  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102259  ldarg.0
0x10225a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::textEdit
0x10225f  ldc.i4.0
0x102260  ldc.i4.s 0x10
0x102262  ldc.i4   0xB6
0x102267  ldc.i4.s 0x18
0x102269  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x10226e  ldarg.0
0x10226f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::textEdit
0x102274  ldc.i4.2
0x102275  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x10227a  ldarg.0
0x10227b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::textEdit
0x102280  ldarg.0
0x102281  ldftn    instance void ButtonColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102287  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x10228c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x102291  ldarg.0
0x102292  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::textEdit
0x102297  ldstr    aButtoncolumnte_0// "ButtonColumnTextEdit"
0x10229c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1022a1  ldloc.1
0x1022a2  ldc.i4.0
0x1022a3  ldc.i4.s 0x28
0x1022a5  ldc.i4   0xA0
0x1022aa  ldc.i4.s 0xE
0x1022ac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1022b1  ldloc.1
0x1022b2  ldstr    aDgcolBcDatatex// "DGCol_BC_DataTextField"
0x1022b7  call     string System.Design.SR::GetString(string name)
0x1022bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1022c1  ldloc.1
0x1022c2  ldc.i4.0
0x1022c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x1022c8  ldloc.1
0x1022c9  ldc.i4.3
0x1022ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1022cf  ldloc.1
0x1022d0  ldstr    aButtoncolumnda// "ButtonColumnDataTextFieldLabel"
0x1022d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1022da  ldarg.0
0x1022db  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox ButtonColumnEditor::dataTextFieldCombo
0x1022e0  ldc.i4.0
0x1022e1  ldc.i4.s 0x38
0x1022e3  ldc.i4   0xB6
0x1022e8  ldc.i4.s 0x15
0x1022ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1022ef  ldarg.0
0x1022f0  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox ButtonColumnEditor::dataTextFieldCombo
0x1022f5  ldc.i4.4
0x1022f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1022fb  ldarg.0
0x1022fc  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox ButtonColumnEditor::dataTextFieldCombo
0x102301  ldc.i4.2
0x102302  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x102307  ldarg.0
0x102308  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox ButtonColumnEditor::dataTextFieldCombo
0x10230d  ldarg.0
0x10230e  ldftn    instance void ButtonColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102314  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x102319  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x10231e  ldarg.0
0x10231f  ldfld    class System.Web.UI.Design.Util.UnsettableComboBox ButtonColumnEditor::dataTextFieldCombo
0x102324  ldstr    aButtoncolumnda_0// "ButtonColumnDataTextFieldCombo"
0x102329  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x10232e  ldarg.0
0x10232f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFieldEdit
0x102334  ldc.i4.0
0x102335  ldc.i4.s 0x38
0x102337  ldc.i4   0xB6
0x10233c  ldc.i4.s 0xE
0x10233e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102343  ldarg.0
0x102344  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFieldEdit
0x102349  ldc.i4.4
0x10234a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x10234f  ldarg.0
0x102350  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFieldEdit
0x102355  ldarg.0
0x102356  ldftn    instance void ButtonColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x10235c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x102361  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x102366  ldarg.0
0x102367  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFieldEdit
0x10236c  ldstr    aButtoncolumnda_1// "ButtonColumnDataTextFieldEdit"
0x102371  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102376  ldloc.2
0x102377  ldc.i4.0
0x102378  ldc.i4.s 0x52
0x10237a  ldc.i4   0xB6
0x10237f  ldc.i4.s 0xE
0x102381  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102386  ldloc.2
0x102387  ldstr    aDgcolBcDatatex_0// "DGCol_BC_DataTextFormat"
0x10238c  call     string System.Design.SR::GetString(string name)
0x102391  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x102396  ldloc.2
0x102397  ldc.i4.5
0x102398  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x10239d  ldloc.2
0x10239e  ldc.i4.0
0x10239f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x1023a4  ldloc.2
0x1023a5  ldstr    aButtoncolumnda_2// "ButtonColumnDataTextFormatStringLabel"
0x1023aa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1023af  ldarg.0
0x1023b0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFormatStringEdit
0x1023b5  ldc.i4.0
0x1023b6  ldc.i4.s 0x62
0x1023b8  ldc.i4   0xB6
0x1023bd  ldc.i4.s 0xE
0x1023bf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1023c4  ldarg.0
0x1023c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFormatStringEdit
0x1023ca  ldc.i4.6
0x1023cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1023d0  ldarg.0
0x1023d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFormatStringEdit
0x1023d6  ldarg.0
0x1023d7  ldftn    instance void ButtonColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x1023dd  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x1023e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x1023e7  ldarg.0
0x1023e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::dataTextFormatStringEdit
0x1023ed  ldstr    aButtoncolumdat// "ButtonColumDataTextFormatStringEdit"
0x1023f2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1023f7  ldloc.3
0x1023f8  ldc.i4   0xC8
0x1023fd  ldc.i4.0
0x1023fe  ldc.i4   0xA0
0x102403  ldc.i4.s 0xE
0x102405  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x10240a  ldloc.3
0x10240b  ldstr    aDgcolBcCommand// "DGCol_BC_Command"
0x102410  call     string System.Design.SR::GetString(string name)
0x102415  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x10241a  ldloc.3
0x10241b  ldc.i4.0
0x10241c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x102421  ldloc.3
0x102422  ldc.i4.8
0x102423  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102428  ldloc.3
0x102429  ldstr    aButtoncolumnco// "ButtonColumnCommandLabel"
0x10242e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102433  ldarg.0
0x102434  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::commandEdit
0x102439  ldc.i4   0xC8
0x10243e  ldc.i4.s 0x10
0x102440  ldc.i4   0xB6
0x102445  ldc.i4.s 0x18
0x102447  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x10244c  ldarg.0
0x10244d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::commandEdit
0x102452  ldc.i4.s 9
0x102454  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102459  ldarg.0
0x10245a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::commandEdit
0x10245f  ldarg.0
0x102460  ldftn    instance void ButtonColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102466  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x10246b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x102470  ldarg.0
0x102471  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::commandEdit
0x102476  ldstr    aButtoncolumnco_0// "ButtonColumnCommandEdit"
0x10247b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x102480  ldloc.s  4
0x102482  ldc.i4   0xC8
0x102487  ldc.i4.s 0x28
0x102489  ldc.i4   0xA0
0x10248e  ldc.i4.s 0xE
0x102490  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x102495  ldloc.s  4
0x102497  ldstr    aDgcolBcButtont// "DGCol_BC_ButtonType"
0x10249c  call     string System.Design.SR::GetString(string name)
0x1024a1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x1024a6  ldloc.s  4
0x1024a8  ldc.i4.0
0x1024a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TabStop(bool)
0x1024ae  ldloc.s  4
0x1024b0  ldc.i4.s 0xA
0x1024b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x1024b7  ldloc.s  4
0x1024b9  ldstr    aButtoncolumnbu// "ButtonColumnButtonTypeLabel"
0x1024be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1024c3  ldarg.0
0x1024c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonColumnEditor::buttonTypeCombo
0x1024c9  ldc.i4   0xC8
0x1024ce  ldc.i4.s 0x38
0x1024d0  ldc.i4   0xB6
0x1024d5  ldc.i4.s 0x15
0x1024d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SetBounds(int32, int32, int32, int32)
0x1024dc  ldarg.0
0x1024dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonColumnEditor::buttonTypeCombo
0x1024e2  ldc.i4.2
0x1024e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x1024e8  ldarg.0
0x1024e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonColumnEditor::buttonTypeCombo
0x1024ee  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection [System.Windows.Forms]System.Windows.Forms.ComboBox::get_Items()
0x1024f3  ldc.i4.2
0x1024f4  newarr   [mscorlib]System.Object
0x1024f9  dup
0x1024fa  ldc.i4.0
0x1024fb  ldstr    aDgcolBcBtLink// "DGCol_BC_BT_Link"
0x102500  call     string System.Design.SR::GetString(string name)
0x102505  stelem.ref
0x102506  dup
0x102507  ldc.i4.1
0x102508  ldstr    aDgcolBcBtPush// "DGCol_BC_BT_Push"
0x10250d  call     string System.Design.SR::GetString(string name)
0x102512  stelem.ref
0x102513  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox/ObjectCollection::AddRange(object[])
0x102518  ldarg.0
0x102519  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonColumnEditor::buttonTypeCombo
0x10251e  ldc.i4.s 0xB
0x102520  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x102525  ldarg.0
0x102526  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonColumnEditor::buttonTypeCombo
0x10252b  ldarg.0
0x10252c  ldftn    instance void ButtonColumnEditor::OnColumnChanged(object source, class [mscorlib]System.EventArgs e)
0x102532  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x102537  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x10253c  ldarg.0
0x10253d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonColumnEditor::buttonTypeCombo
0x102542  ldstr    aButtoncolumnbu_0// "ButtonColumnButtonTypeCombo"
0x102547  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x10254c  ldarg.0
0x10254d  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x102552  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Clear()
0x102557  ldarg.0
0x102558  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x10255d  ldc.i4.s 0xB
0x10255f  newarr   [System.Windows.Forms]System.Windows.Forms.Control
0x102564  dup
0x102565  ldc.i4.0
0x102566  ldarg.0
0x102567  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ButtonColumnEditor::buttonTypeCombo
0x10256c  stelem.ref
0x10256d  dup
0x10256e  ldc.i4.1
0x10256f  ldloc.s  4
0x102571  stelem.ref
0x102572  dup
0x102573  ldc.i4.2
0x102574  ldarg.0
0x102575  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox ButtonColumnEditor::commandEdit
0x10257a  stelem.ref
0x10257b  dup
0x10257c  ldc.i4.3
0x10257d  ldloc.3
0x10257e  stelem.ref
0x10257f  dup
0x102580  ldc.i4.4
  ... truncated ...
```
