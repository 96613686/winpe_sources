# System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::InitializeComponent

- ea: `0x40550`
- end: `0x40a88`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::InitializeComponent`
- size: `1336`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x40350`

## callees

- `0x51a90`

## string_xrefs

- `0x406af`: `_commandTextBox`
- `0x4063e`: `_commandLabel`

## pseudocode

```c

```

## disassembly

```asm
0x40550  newobj   instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewTextBoxColumn::.ctor()
0x40555  stloc.0
0x40556  newobj   instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewCellStyle::.ctor()
0x4055b  stloc.1
0x4055c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewComboBoxColumn::.ctor()
0x40561  stloc.2
0x40562  newobj   instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewComboBoxColumn::.ctor()
0x40567  stloc.3
0x40568  newobj   instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewTextBoxColumn::.ctor()
0x4056d  stloc.s  4
0x4056f  ldarg.0
0x40570  newobj   instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::.ctor()
0x40575  stfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x4057a  ldarg.0
0x4057b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x40580  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_okButton
0x40585  ldarg.0
0x40586  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x4058b  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x40590  ldarg.0
0x40591  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x40596  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandLabel
0x4059b  ldarg.0
0x4059c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x405a1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_helpLabel
0x405a6  ldarg.0
0x405a7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x405ac  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_cancelButton
0x405b1  ldarg.0
0x405b2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x405b7  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersLabel
0x405bc  ldarg.0
0x405bd  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x405c2  ldarg.0
0x405c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_helpLabel
0x405c8  ldc.i4.s 0xD
0x405ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x405cf  ldarg.0
0x405d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_helpLabel
0x405d5  ldc.i4.s 0xC
0x405d7  ldc.i4.s 0xC
0x405d9  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x405de  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x405e3  ldarg.0
0x405e4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_helpLabel
0x405e9  ldstr    aHelplabel// "_helpLabel"
0x405ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x405f3  ldarg.0
0x405f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_helpLabel
0x405f9  ldc.i4   0x240
0x405fe  ldc.i4.s 0x2F
0x40600  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x40605  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x4060a  ldarg.0
0x4060b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_helpLabel
0x40610  ldc.i4.s 0xA
0x40612  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x40617  ldarg.0
0x40618  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandLabel
0x4061d  ldc.i4.s 0xD
0x4061f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x40624  ldarg.0
0x40625  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandLabel
0x4062a  ldc.i4.s 0xC
0x4062c  ldc.i4.s 0x40
0x4062e  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x40633  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x40638  ldarg.0
0x40639  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandLabel
0x4063e  ldstr    aCommandlabel// "_commandLabel"
0x40643  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x40648  ldarg.0
0x40649  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandLabel
0x4064e  ldc.i4   0x240
0x40653  ldc.i4.s 0x10
0x40655  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x4065a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x4065f  ldarg.0
0x40660  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandLabel
0x40665  ldc.i4.s 0x14
0x40667  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4066c  ldarg.0
0x4066d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x40672  ldc.i4.s 0xD
0x40674  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x40679  ldarg.0
0x4067a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x4067f  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0x40684  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0x40689  ldarg.0
0x4068a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x4068f  ldc.i4.s 0xC
0x40691  ldc.i4.s 0x52
0x40693  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x40698  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x4069d  ldarg.0
0x4069e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x406a3  ldc.i4.1
0x406a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_Multiline(bool)
0x406a9  ldarg.0
0x406aa  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x406af  ldstr    aCommandtextbox// "_commandTextBox"
0x406b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x406b9  ldarg.0
0x406ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x406bf  ldc.i4.1
0x406c0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_ReadOnly(bool)
0x406c5  ldarg.0
0x406c6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x406cb  ldc.i4.2
0x406cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_ScrollBars(valuetype [System.Windows.Forms]System.Windows.Forms.ScrollBars)
0x406d1  ldarg.0
0x406d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x406d7  ldc.i4   0x240
0x406dc  ldc.i4.s 0x32
0x406de  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x406e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x406e8  ldarg.0
0x406e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_commandTextBox
0x406ee  ldc.i4.s 0x1E
0x406f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x406f5  ldarg.0
0x406f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersLabel
0x406fb  ldc.i4.s 0xD
0x406fd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x40702  ldarg.0
0x40703  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersLabel
0x40708  ldc.i4.s 0xD
0x4070a  ldc.i4   0x8E
0x4070f  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x40714  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x40719  ldarg.0
0x4071a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersLabel
0x4071f  ldstr    aParameterslabe// "_parametersLabel"
0x40724  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x40729  ldarg.0
0x4072a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersLabel
0x4072f  ldc.i4   0x240
0x40734  ldc.i4.s 0x10
0x40736  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x4073b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x40740  ldarg.0
0x40741  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersLabel
0x40746  ldc.i4.s 0x28
0x40748  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4074d  ldarg.0
0x4074e  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x40753  ldc.i4.0
0x40754  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_AllowUserToAddRows(bool)
0x40759  ldarg.0
0x4075a  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x4075f  ldc.i4.0
0x40760  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_AllowUserToDeleteRows(bool)
0x40765  ldarg.0
0x40766  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x4076b  ldc.i4.s 0xF
0x4076d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x40772  ldarg.0
0x40773  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x40778  ldc.i4.0
0x40779  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_AutoGenerateColumns(bool)
0x4077e  ldarg.0
0x4077f  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x40784  ldc.i4.1
0x40785  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_ColumnHeadersHeightSizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode)
0x4078a  ldloc.0
0x4078b  ldstr    aName_1// "Name"
0x40790  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_DataPropertyName(string)
0x40795  ldloc.0
0x40796  ldloc.1
0x40797  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewBand::set_DefaultCellStyle(class [System.Windows.Forms]System.Windows.Forms.DataGridViewCellStyle)
0x4079c  ldloc.0
0x4079d  ldstr    aParameternamec// "_parameterNameColumn"
0x407a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_Name(string)
0x407a7  ldloc.0
0x407a8  ldc.i4.1
0x407a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewBand::set_ReadOnly(bool)
0x407ae  ldloc.0
0x407af  ldtoken  [mscorlib]System.String
0x407b4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x407b9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_ValueType(class [mscorlib]System.Type)
0x407be  ldloc.2
0x407bf  ldstr    aType_0// "Type"
0x407c4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_DataPropertyName(string)
0x407c9  ldloc.2
0x407ca  ldloc.1
0x407cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewBand::set_DefaultCellStyle(class [System.Windows.Forms]System.Windows.Forms.DataGridViewCellStyle)
0x407d0  ldloc.2
0x407d1  ldstr    aParametertypec_0// "_parameterTypeColumn"
0x407d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_Name(string)
0x407db  ldloc.2
0x407dc  ldtoken  [mscorlib]System.String
0x407e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x407e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_ValueType(class [mscorlib]System.Type)
0x407eb  ldloc.3
0x407ec  ldstr    aDbtype// "DbType"
0x407f1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_DataPropertyName(string)
0x407f6  ldloc.3
0x407f7  ldloc.1
0x407f8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewBand::set_DefaultCellStyle(class [System.Windows.Forms]System.Windows.Forms.DataGridViewCellStyle)
0x407fd  ldloc.3
0x407fe  ldstr    aParameterdbtyp// "_parameterDbTypeColumn"
0x40803  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_Name(string)
0x40808  ldloc.3
0x40809  ldtoken  [mscorlib]System.String
0x4080e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40813  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_ValueType(class [mscorlib]System.Type)
0x40818  ldloc.s  4
0x4081a  ldstr    aDefaultvalue// "DefaultValue"
0x4081f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_DataPropertyName(string)
0x40824  ldloc.s  4
0x40826  ldloc.1
0x40827  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewBand::set_DefaultCellStyle(class [System.Windows.Forms]System.Windows.Forms.DataGridViewCellStyle)
0x4082c  ldloc.s  4
0x4082e  ldstr    aParametervalue// "_parameterValueColumn"
0x40833  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_Name(string)
0x40838  ldloc.s  4
0x4083a  ldtoken  [mscorlib]System.String
0x4083f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40844  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn::set_ValueType(class [mscorlib]System.Type)
0x40849  ldarg.0
0x4084a  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x4084f  ldc.i4.0
0x40850  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_EditMode(valuetype [System.Windows.Forms]System.Windows.Forms.DataGridViewEditMode)
0x40855  ldarg.0
0x40856  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x4085b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection [System.Windows.Forms]System.Windows.Forms.DataGridView::get_Columns()
0x40860  ldloc.0
0x40861  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection::Add(class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn)
0x40866  pop
0x40867  ldarg.0
0x40868  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x4086d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection [System.Windows.Forms]System.Windows.Forms.DataGridView::get_Columns()
0x40872  ldloc.2
0x40873  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection::Add(class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn)
0x40878  pop
0x40879  ldarg.0
0x4087a  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x4087f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection [System.Windows.Forms]System.Windows.Forms.DataGridView::get_Columns()
0x40884  ldloc.3
0x40885  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection::Add(class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn)
0x4088a  pop
0x4088b  ldarg.0
0x4088c  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x40891  callvirt instance class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection [System.Windows.Forms]System.Windows.Forms.DataGridView::get_Columns()
0x40896  ldloc.s  4
0x40898  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.DataGridViewColumnCollection::Add(class [System.Windows.Forms]System.Windows.Forms.DataGridViewColumn)
0x4089d  pop
0x4089e  ldarg.0
0x4089f  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x408a4  ldc.i4.s 0xC
0x408a6  ldc.i4   0xA0
0x408ab  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x408b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x408b5  ldarg.0
0x408b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x408bb  ldc.i4.0
0x408bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_MultiSelect(bool)
0x408c1  ldarg.0
0x408c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x408c7  ldstr    aParametersdata// "_parametersDataGridView"
0x408cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x408d1  ldarg.0
0x408d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x408d7  ldc.i4.0
0x408d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.DataGridView::set_RowHeadersVisible(bool)
0x408dd  ldarg.0
0x408de  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x408e3  ldc.i4   0x240
0x408e8  ldc.i4   0x9C
0x408ed  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x408f2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x408f7  ldarg.0
0x408f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.DataGridView System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_parametersDataGridView
0x408fd  ldc.i4.s 0x32
0x408ff  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x40904  ldarg.0
0x40905  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_okButton
0x4090a  ldc.i4.s 0xA
0x4090c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x40911  ldarg.0
0x40912  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_okButton
0x40917  ldc.i4   0x1B0
0x4091c  ldc.i4   0x14B
0x40921  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x40926  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x4092b  ldarg.0
0x4092c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_okButton
0x40931  ldstr    aOkbutton// "_okButton"
0x40936  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4093b  ldarg.0
0x4093c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_okButton
0x40941  ldc.i4.s 0x3C
0x40943  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x40948  ldarg.0
0x40949  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::_okButton
0x4094e  ldarg.0
0x4094f  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceRefreshSchemaForm::OnOkButtonClick(object sender, class [mscorlib]System.EventArgs e)
0x40955  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4095a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
  ... truncated ...
```
