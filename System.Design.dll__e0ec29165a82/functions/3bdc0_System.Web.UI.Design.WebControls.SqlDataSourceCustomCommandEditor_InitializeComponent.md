# System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::InitializeComponent

- ea: `0x3bdc0`
- end: `0x3c1de`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::InitializeComponent`
- size: `1054`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3bd20`

## callees

- `0x518a0`

## string_xrefs

- `0x3c019`: `_commandTextBox`
- `0x3c10a`: `_storedProcedureComboBox`
- `0x3c194`: `SqlDataSourceCustomCommandEditor`

## pseudocode

```c

```

## disassembly

```asm
0x3bdc0  ldarg.0
0x3bdc1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x3bdc6  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3bdcb  ldarg.0
0x3bdcc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x3bdd1  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3bdd6  ldarg.0
0x3bdd7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x3bddc  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3bde1  ldarg.0
0x3bde2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x3bde7  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureRadioButton
0x3bdec  ldarg.0
0x3bded  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x3bdf2  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3bdf7  ldarg.0
0x3bdf8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x3bdfd  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3be02  ldarg.0
0x3be03  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x3be08  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3be0d  ldarg.0
0x3be0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3be13  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3be18  ldarg.0
0x3be19  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3be1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3be23  ldarg.0
0x3be24  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3be29  ldarg.0
0x3be2a  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3be2f  ldc.i4.s 0xD
0x3be31  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3be36  ldarg.0
0x3be37  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3be3c  ldc.i4.s 0xC
0x3be3e  ldc.i4.s 0xC
0x3be40  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3be45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3be4a  ldarg.0
0x3be4b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3be50  ldstr    aSqlradiobutton// "_sqlRadioButton"
0x3be55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3be5a  ldarg.0
0x3be5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3be60  ldc.i4   0x1E9
0x3be65  ldc.i4.s 0x14
0x3be67  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3be6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3be71  ldarg.0
0x3be72  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3be77  ldc.i4.s 0xA
0x3be79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3be7e  ldarg.0
0x3be7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3be84  ldarg.0
0x3be85  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::OnSqlRadioButtonCheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x3be8b  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x3be90  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x3be95  ldarg.0
0x3be96  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3be9b  ldc.i4.s 0xF
0x3be9d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3bea2  ldarg.0
0x3bea3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3bea8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3bead  ldarg.0
0x3beae  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3beb3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3beb8  ldarg.0
0x3beb9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3bebe  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3bec3  ldarg.0
0x3bec4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3bec9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3bece  ldarg.0
0x3becf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3bed4  ldc.i4.s 0x1C
0x3bed6  ldc.i4.s 0x20
0x3bed8  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3bedd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3bee2  ldarg.0
0x3bee3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3bee8  ldstr    aSqlpanel// "_sqlPanel"
0x3beed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3bef2  ldarg.0
0x3bef3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3bef8  ldc.i4   0x1E0
0x3befd  ldc.i4.s 0x79
0x3beff  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3bf04  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3bf09  ldarg.0
0x3bf0a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3bf0f  ldc.i4.s 0x14
0x3bf11  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3bf16  ldarg.0
0x3bf17  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureRadioButton
0x3bf1c  ldc.i4.s 0xE
0x3bf1e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3bf23  ldarg.0
0x3bf24  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureRadioButton
0x3bf29  ldc.i4.s 0xC
0x3bf2b  ldc.i4   0xA0
0x3bf30  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3bf35  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3bf3a  ldarg.0
0x3bf3b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureRadioButton
0x3bf40  ldstr    aStoredprocedur// "_storedProcedureRadioButton"
0x3bf45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3bf4a  ldarg.0
0x3bf4b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureRadioButton
0x3bf50  ldc.i4   0x1E9
0x3bf55  ldc.i4.s 0x14
0x3bf57  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3bf5c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3bf61  ldarg.0
0x3bf62  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureRadioButton
0x3bf67  ldc.i4.s 0x1E
0x3bf69  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3bf6e  ldarg.0
0x3bf6f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3bf74  ldc.i4.s 0xE
0x3bf76  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3bf7b  ldarg.0
0x3bf7c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3bf81  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3bf86  ldarg.0
0x3bf87  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3bf8c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3bf91  ldarg.0
0x3bf92  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3bf97  ldc.i4.s 0x1C
0x3bf99  ldc.i4   0xB4
0x3bf9e  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3bfa3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3bfa8  ldarg.0
0x3bfa9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3bfae  ldstr    aStoredprocedur_0// "_storedProcedurePanel"
0x3bfb3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3bfb8  ldarg.0
0x3bfb9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3bfbe  ldc.i4   0x109
0x3bfc3  ldc.i4.s 0x15
0x3bfc5  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3bfca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3bfcf  ldarg.0
0x3bfd0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3bfd5  ldc.i4.s 0x28
0x3bfd7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3bfdc  ldarg.0
0x3bfdd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3bfe2  ldc.i4.1
0x3bfe3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_AcceptsReturn(bool)
0x3bfe8  ldarg.0
0x3bfe9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3bfee  ldc.i4.s 0xF
0x3bff0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3bff5  ldarg.0
0x3bff6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3bffb  ldc.i4.0
0x3bffc  ldc.i4.0
0x3bffd  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3c002  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3c007  ldarg.0
0x3c008  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3c00d  ldc.i4.1
0x3c00e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_Multiline(bool)
0x3c013  ldarg.0
0x3c014  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3c019  ldstr    aCommandtextbox// "_commandTextBox"
0x3c01e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3c023  ldarg.0
0x3c024  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3c029  ldc.i4.2
0x3c02a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_ScrollBars(valuetype [System.Windows.Forms]System.Windows.Forms.ScrollBars)
0x3c02f  ldarg.0
0x3c030  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3c035  ldc.i4   0x1E0
0x3c03a  ldc.i4.s 0x5D
0x3c03c  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3c041  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3c046  ldarg.0
0x3c047  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3c04c  ldc.i4.s 0x14
0x3c04e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3c053  ldarg.0
0x3c054  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_commandTextBox
0x3c059  ldarg.0
0x3c05a  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::OnCommandTextBoxTextChanged(object sender, class [mscorlib]System.EventArgs e)
0x3c060  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x3c065  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x3c06a  ldarg.0
0x3c06b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3c070  ldc.i4.s 0xA
0x3c072  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3c077  ldarg.0
0x3c078  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3c07d  ldc.i4   0x14A
0x3c082  ldc.i4.s 0x62
0x3c084  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3c089  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3c08e  ldarg.0
0x3c08f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3c094  ldstr    aQuerybuilderbu// "_queryBuilderButton"
0x3c099  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3c09e  ldarg.0
0x3c09f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3c0a4  ldc.i4   0x96
0x3c0a9  ldc.i4.s 0x17
0x3c0ab  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3c0b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3c0b5  ldarg.0
0x3c0b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3c0bb  ldc.i4.s 0x1E
0x3c0bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3c0c2  ldarg.0
0x3c0c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_queryBuilderButton
0x3c0c8  ldarg.0
0x3c0c9  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::OnQueryBuilderButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x3c0cf  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x3c0d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x3c0d9  ldarg.0
0x3c0da  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3c0df  ldc.i4.s 0xF
0x3c0e1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3c0e6  ldarg.0
0x3c0e7  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3c0ec  ldc.i4.2
0x3c0ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x3c0f2  ldarg.0
0x3c0f3  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3c0f8  ldc.i4.0
0x3c0f9  ldc.i4.0
0x3c0fa  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3c0ff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3c104  ldarg.0
0x3c105  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3c10a  ldstr    aStoredprocedur_1// "_storedProcedureComboBox"
0x3c10f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3c114  ldarg.0
0x3c115  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3c11a  ldc.i4   0x109
0x3c11f  ldc.i4.s 0x15
0x3c121  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3c126  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3c12b  ldarg.0
0x3c12c  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3c131  ldc.i4.s 0xA
0x3c133  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3c138  ldarg.0
0x3c139  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureComboBox
0x3c13e  ldarg.0
0x3c13f  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::OnStoredProcedureComboBoxSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x3c145  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x3c14a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x3c14f  ldarg.0
0x3c150  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3c155  ldarg.0
0x3c156  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlRadioButton
0x3c15b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3c160  ldarg.0
0x3c161  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3c166  ldarg.0
0x3c167  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3c16c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3c171  ldarg.0
0x3c172  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3c177  ldarg.0
0x3c178  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedureRadioButton
0x3c17d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3c182  ldarg.0
0x3c183  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3c188  ldarg.0
0x3c189  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3c18e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3c193  ldarg.0
0x3c194  ldstr    aSqldatasourcec_43// "SqlDataSourceCustomCommandEditor"
0x3c199  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3c19e  ldarg.0
0x3c19f  ldc.i4   0x20A
0x3c1a4  ldc.i4   0xE6
0x3c1a9  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3c1ae  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3c1b3  ldarg.0
0x3c1b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_storedProcedurePanel
0x3c1b9  ldc.i4.0
0x3c1ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x3c1bf  ldarg.0
0x3c1c0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3c1c5  ldc.i4.0
0x3c1c6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x3c1cb  ldarg.0
0x3c1cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceCustomCommandEditor::_sqlPanel
0x3c1d1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x3c1d6  ldarg.0
0x3c1d7  ldc.i4.0
0x3c1d8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x3c1dd  ret
```
