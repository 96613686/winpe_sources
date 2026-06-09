# System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::InitializeComponent

- ea: `0x36340`
- end: `0x36ddd`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::InitializeComponent`
- size: `2717`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x35fb0`

## callees

- `0x518a0`
- `0x51a90`

## string_xrefs

- `0x36505`: `_columnsComboBox`
- `0x365c4`: `_operatorsComboBox`
- `0x3667d`: `_sourceComboBox`
- `0x36b02`: `_removeButton`
- `0x36dac`: `SqlDataSourceConfigureFilterForm`

## pseudocode

```c

```

## disassembly

```asm
0x36340  ldarg.0
0x36341  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x36346  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_helpLabel
0x3634b  ldarg.0
0x3634c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x36351  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnLabel
0x36356  ldarg.0
0x36357  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x3635c  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnsComboBox
0x36361  ldarg.0
0x36362  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x36367  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorsComboBox
0x3636c  ldarg.0
0x3636d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x36372  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorLabel
0x36377  ldarg.0
0x36378  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x3637d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_whereClausesLabel
0x36382  ldarg.0
0x36383  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x36388  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_addButton
0x3638d  ldarg.0
0x3638e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x36393  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_removeButton
0x36398  ldarg.0
0x36399  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x3639e  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_cancelButton
0x363a3  ldarg.0
0x363a4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x363a9  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_okButton
0x363ae  ldarg.0
0x363af  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x363b4  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_expressionLabel
0x363b9  ldarg.0
0x363ba  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x363bf  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x363c4  ldarg.0
0x363c5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x363ca  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesPanel
0x363cf  ldarg.0
0x363d0  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x363d5  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceComboBox
0x363da  ldarg.0
0x363db  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x363e0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceLabel
0x363e5  ldarg.0
0x363e6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x363eb  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_expressionTextBox
0x363f0  ldarg.0
0x363f1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x363f6  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_whereClausesListView
0x363fb  ldarg.0
0x363fc  ldstr    asc_12DF92// ""
0x36401  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor(string)
0x36406  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_expressionColumnHeader
0x3640b  ldarg.0
0x3640c  ldstr    asc_12DF92// ""
0x36411  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor(string)
0x36416  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_valueColumnHeader
0x3641b  ldarg.0
0x3641c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x36421  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_valueTextBox
0x36426  ldarg.0
0x36427  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x3642c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_valueLabel
0x36431  ldarg.0
0x36432  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x36437  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3643c  ldarg.0
0x3643d  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x36442  ldarg.0
0x36443  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_helpLabel
0x36448  ldc.i4.s 0xD
0x3644a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3644f  ldarg.0
0x36450  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_helpLabel
0x36455  ldc.i4.s 0xC
0x36457  ldc.i4.s 0xB
0x36459  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3645e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x36463  ldarg.0
0x36464  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_helpLabel
0x36469  ldstr    aHelplabel// "_helpLabel"
0x3646e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x36473  ldarg.0
0x36474  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_helpLabel
0x36479  ldc.i4   0x20C
0x3647e  ldc.i4.s 0x2A
0x36480  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x36485  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3648a  ldarg.0
0x3648b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_helpLabel
0x36490  ldc.i4.s 0xA
0x36492  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x36497  ldarg.0
0x36498  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnLabel
0x3649d  ldc.i4.s 0xC
0x3649f  ldc.i4.s 0x3B
0x364a1  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x364a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x364ab  ldarg.0
0x364ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnLabel
0x364b1  ldstr    aColumnlabel// "_columnLabel"
0x364b6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x364bb  ldarg.0
0x364bc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnLabel
0x364c1  ldc.i4   0xAC
0x364c6  ldc.i4.s 0xF
0x364c8  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x364cd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x364d2  ldarg.0
0x364d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnLabel
0x364d8  ldc.i4.s 0x14
0x364da  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x364df  ldarg.0
0x364e0  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnsComboBox
0x364e5  ldc.i4.2
0x364e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x364eb  ldarg.0
0x364ec  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnsComboBox
0x364f1  ldc.i4.s 0xC
0x364f3  ldc.i4.s 0x4D
0x364f5  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x364fa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x364ff  ldarg.0
0x36500  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnsComboBox
0x36505  ldstr    aColumnscombobo// "_columnsComboBox"
0x3650a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3650f  ldarg.0
0x36510  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnsComboBox
0x36515  ldc.i4   0xAC
0x3651a  ldc.i4.s 0x15
0x3651c  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x36521  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x36526  ldarg.0
0x36527  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnsComboBox
0x3652c  ldc.i4.1
0x3652d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_Sorted(bool)
0x36532  ldarg.0
0x36533  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnsComboBox
0x36538  ldc.i4.s 0x1E
0x3653a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3653f  ldarg.0
0x36540  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_columnsComboBox
0x36545  ldarg.0
0x36546  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::OnColumnsComboBoxSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x3654c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x36551  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x36556  ldarg.0
0x36557  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorLabel
0x3655c  ldc.i4.s 0xC
0x3655e  ldc.i4.s 0x68
0x36560  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x36565  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3656a  ldarg.0
0x3656b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorLabel
0x36570  ldstr    aOperatorlabel// "_operatorLabel"
0x36575  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3657a  ldarg.0
0x3657b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorLabel
0x36580  ldc.i4   0xAC
0x36585  ldc.i4.s 0xF
0x36587  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3658c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x36591  ldarg.0
0x36592  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorLabel
0x36597  ldc.i4.s 0x28
0x36599  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3659e  ldarg.0
0x3659f  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorsComboBox
0x365a4  ldc.i4.2
0x365a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x365aa  ldarg.0
0x365ab  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorsComboBox
0x365b0  ldc.i4.s 0xC
0x365b2  ldc.i4.s 0x7A
0x365b4  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x365b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x365be  ldarg.0
0x365bf  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorsComboBox
0x365c4  ldstr    aOperatorscombo// "_operatorsComboBox"
0x365c9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x365ce  ldarg.0
0x365cf  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorsComboBox
0x365d4  ldc.i4   0xAC
0x365d9  ldc.i4.s 0x15
0x365db  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x365e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x365e5  ldarg.0
0x365e6  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorsComboBox
0x365eb  ldc.i4.s 0x32
0x365ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x365f2  ldarg.0
0x365f3  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_operatorsComboBox
0x365f8  ldarg.0
0x365f9  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::OnOperatorsComboBoxSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x365ff  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x36604  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x36609  ldarg.0
0x3660a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceLabel
0x3660f  ldc.i4.s 0xC
0x36611  ldc.i4   0x94
0x36616  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3661b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x36620  ldarg.0
0x36621  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceLabel
0x36626  ldstr    aSourcelabel// "_sourceLabel"
0x3662b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x36630  ldarg.0
0x36631  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceLabel
0x36636  ldc.i4   0xAC
0x3663b  ldc.i4.s 0xF
0x3663d  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x36642  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x36647  ldarg.0
0x36648  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceLabel
0x3664d  ldc.i4.s 0x3C
0x3664f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x36654  ldarg.0
0x36655  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceComboBox
0x3665a  ldc.i4.2
0x3665b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x36660  ldarg.0
0x36661  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceComboBox
0x36666  ldc.i4.s 0xC
0x36668  ldc.i4   0xA6
0x3666d  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x36672  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x36677  ldarg.0
0x36678  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceComboBox
0x3667d  ldstr    aSourcecombobox// "_sourceComboBox"
0x36682  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x36687  ldarg.0
0x36688  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceComboBox
0x3668d  ldc.i4   0xAC
0x36692  ldc.i4.s 0x15
0x36694  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x36699  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3669e  ldarg.0
0x3669f  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceComboBox
0x366a4  ldc.i4.s 0x46
0x366a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x366ab  ldarg.0
0x366ac  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_sourceComboBox
0x366b1  ldarg.0
0x366b2  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::OnSourceComboBoxSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x366b8  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x366bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x366c2  ldarg.0
0x366c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x366c8  ldc.i4.s 0xD
0x366ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x366cf  ldarg.0
0x366d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x366d5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x366da  ldarg.0
0x366db  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesPanel
0x366e0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x366e5  ldarg.0
0x366e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x366eb  ldc.i4   0xF3
0x366f0  ldc.i4.s 0x3B
0x366f2  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x366f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x366fc  ldarg.0
0x366fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x36702  ldstr    aPropertiesgrou// "_propertiesGroupBox"
0x36707  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3670c  ldarg.0
0x3670d  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x36712  ldc.i4   0xC2
0x36717  ldc.i4.s 0x7F
0x36719  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3671e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x36723  ldarg.0
0x36724  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x36729  ldc.i4.s 0x50
0x3672b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x36730  ldarg.0
0x36731  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesGroupBox
0x36736  ldc.i4.0
0x36737  callvirt instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::set_TabStop(bool)
0x3673c  ldarg.0
0x3673d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesPanel
0x36742  ldc.i4.s 0xF
0x36744  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x36749  ldarg.0
0x3674a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesPanel
0x3674f  ldc.i4.s 0xA
0x36751  ldc.i4.s 0xF
0x36753  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x36758  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3675d  ldarg.0
0x3675e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesPanel
0x36763  ldstr    aPropertiespane// "_propertiesPanel"
0x36768  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3676d  ldarg.0
0x3676e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureFilterForm::_propertiesPanel
0x36773  ldc.i4   0xA4
0x36778  ldc.i4.s 0x64
  ... truncated ...
```
