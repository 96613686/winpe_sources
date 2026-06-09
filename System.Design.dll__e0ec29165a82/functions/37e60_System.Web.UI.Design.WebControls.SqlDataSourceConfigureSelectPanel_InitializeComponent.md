# System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::InitializeComponent

- ea: `0x37e60`
- end: `0x3890f`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::InitializeComponent`
- size: `2735`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x37db0`

## callees

- `0x518a0`

## string_xrefs

- `0x381a7`: `_tablesComboBox`
- `0x388ae`: `SqlDataSourceConfigureSelectPanel`

## pseudocode

```c

```

## disassembly

```asm
0x37e60  ldarg.0
0x37e61  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x37e66  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x37e6b  ldarg.0
0x37e6c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x37e71  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x37e76  ldarg.0
0x37e77  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x37e7c  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x37e81  ldarg.0
0x37e82  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x37e87  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_advancedOptionsButton
0x37e8c  ldarg.0
0x37e8d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x37e92  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_previewTextBox
0x37e97  ldarg.0
0x37e98  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x37e9d  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_previewLabel
0x37ea2  ldarg.0
0x37ea3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x37ea8  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableNameLabel
0x37ead  ldarg.0
0x37eae  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x37eb3  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_addSortButton
0x37eb8  ldarg.0
0x37eb9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x37ebe  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_addFilterButton
0x37ec3  ldarg.0
0x37ec4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x37ec9  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_selectDistinctCheckBox
0x37ece  ldarg.0
0x37ecf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckedListBox::.ctor()
0x37ed4  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckedListBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsCheckedListBox
0x37ed9  ldarg.0
0x37eda  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x37edf  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsLabel
0x37ee4  ldarg.0
0x37ee5  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x37eea  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x37eef  ldarg.0
0x37ef0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x37ef5  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_columnsTableLayoutPanel
0x37efa  ldarg.0
0x37efb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x37f00  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_optionsTableLayoutPanel
0x37f05  ldarg.0
0x37f06  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x37f0b  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x37f10  ldarg.0
0x37f11  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_columnsTableLayoutPanel
0x37f16  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x37f1b  ldarg.0
0x37f1c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_optionsTableLayoutPanel
0x37f21  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x37f26  ldarg.0
0x37f27  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x37f2c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x37f31  ldarg.0
0x37f32  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x37f37  ldarg.0
0x37f38  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x37f3d  ldc.i4.s 0xD
0x37f3f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x37f44  ldarg.0
0x37f45  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x37f4a  ldc.i4.0
0x37f4b  ldc.i4.0
0x37f4c  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x37f51  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x37f56  ldarg.0
0x37f57  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x37f5c  ldstr    aRetrievedatala// "_retrieveDataLabel"
0x37f61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x37f66  ldarg.0
0x37f67  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x37f6c  ldc.i4   0x220
0x37f71  ldc.i4.s 0x10
0x37f73  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x37f78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x37f7d  ldarg.0
0x37f7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_retrieveDataLabel
0x37f83  ldc.i4.s 0xA
0x37f85  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x37f8a  ldarg.0
0x37f8b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x37f90  ldc.i4.7
0x37f91  ldc.i4.s 0x13
0x37f93  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x37f98  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x37f9d  ldarg.0
0x37f9e  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x37fa3  ldstr    aCustomsqlradio// "_customSqlRadioButton"
0x37fa8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x37fad  ldarg.0
0x37fae  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x37fb3  ldc.i4   0x219
0x37fb8  ldc.i4.s 0x12
0x37fba  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x37fbf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x37fc4  ldarg.0
0x37fc5  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x37fca  ldc.i4.s 0x14
0x37fcc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x37fd1  ldarg.0
0x37fd2  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_customSqlRadioButton
0x37fd7  ldarg.0
0x37fd8  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::OnCustomSqlRadioButtonCheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x37fde  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x37fe3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x37fe8  ldarg.0
0x37fe9  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x37fee  ldc.i4.7
0x37fef  ldc.i4.s 0x26
0x37ff1  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x37ff6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x37ffb  ldarg.0
0x37ffc  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x38001  ldstr    aTableradiobutt// "_tableRadioButton"
0x38006  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3800b  ldarg.0
0x3800c  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x38011  ldc.i4   0x219
0x38016  ldc.i4.s 0x12
0x38018  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3801d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x38022  ldarg.0
0x38023  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x38028  ldc.i4.s 0x1E
0x3802a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3802f  ldarg.0
0x38030  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableRadioButton
0x38035  ldarg.0
0x38036  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::OnTableRadioButtonCheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x3803c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x38041  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x38046  ldarg.0
0x38047  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x3804c  ldc.i4.s 0xF
0x3804e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x38053  ldarg.0
0x38054  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x38059  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3805e  ldarg.0
0x3805f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableNameLabel
0x38064  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x38069  ldarg.0
0x3806a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x3806f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x38074  ldarg.0
0x38075  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x3807a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3807f  ldarg.0
0x38080  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x38085  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3808a  ldarg.0
0x3808b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsLabel
0x38090  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x38095  ldarg.0
0x38096  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x3809b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x380a0  ldarg.0
0x380a1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_columnsTableLayoutPanel
0x380a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x380ab  ldarg.0
0x380ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x380b1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x380b6  ldarg.0
0x380b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_previewLabel
0x380bc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x380c1  ldarg.0
0x380c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x380c7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x380cc  ldarg.0
0x380cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_previewTextBox
0x380d2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x380d7  ldarg.0
0x380d8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x380dd  ldc.i4.s 0x19
0x380df  ldc.i4.s 0x3A
0x380e1  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x380e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x380eb  ldarg.0
0x380ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x380f1  ldstr    aFieldchooserpa// "_fieldChooserPanel"
0x380f6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x380fb  ldarg.0
0x380fc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x38101  ldc.i4   0x207
0x38106  ldc.i4   0xD8
0x3810b  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x38110  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x38115  ldarg.0
0x38116  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldChooserPanel
0x3811b  ldc.i4.s 0x28
0x3811d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x38122  ldarg.0
0x38123  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableNameLabel
0x38128  ldc.i4.s 0xD
0x3812a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3812f  ldarg.0
0x38130  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableNameLabel
0x38135  ldc.i4.0
0x38136  ldc.i4.0
0x38137  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3813c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x38141  ldarg.0
0x38142  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableNameLabel
0x38147  ldstr    aTablenamelabel// "_tableNameLabel"
0x3814c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x38151  ldarg.0
0x38152  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableNameLabel
0x38157  ldc.i4   0x207
0x3815c  ldc.i4.s 0x10
0x3815e  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x38163  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x38168  ldarg.0
0x38169  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tableNameLabel
0x3816e  ldc.i4.s 0xA
0x38170  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x38175  ldarg.0
0x38176  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x3817b  ldc.i4.s 0xD
0x3817d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x38182  ldarg.0
0x38183  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x38188  ldc.i4.2
0x38189  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x3818e  ldarg.0
0x3818f  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x38194  ldc.i4.0
0x38195  ldc.i4.s 0x10
0x38197  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3819c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x381a1  ldarg.0
0x381a2  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x381a7  ldstr    aTablescombobox// "_tablesComboBox"
0x381ac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x381b1  ldarg.0
0x381b2  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x381b7  ldc.i4   0x107
0x381bc  ldc.i4.s 0x15
0x381be  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x381c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x381c8  ldarg.0
0x381c9  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x381ce  ldc.i4.s 0x14
0x381d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x381d5  ldarg.0
0x381d6  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_tablesComboBox
0x381db  ldarg.0
0x381dc  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::OnTablesComboBoxSelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x381e2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x381e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x381ec  ldarg.0
0x381ed  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsLabel
0x381f2  ldc.i4.s 0xD
0x381f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x381f9  ldarg.0
0x381fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsLabel
0x381ff  ldc.i4.0
0x38200  ldc.i4.s 0x2A
0x38202  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x38207  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3820c  ldarg.0
0x3820d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsLabel
0x38212  ldstr    aFieldslabel// "_fieldsLabel"
0x38217  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3821c  ldarg.0
0x3821d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsLabel
0x38222  ldc.i4   0x207
0x38227  ldc.i4.s 0x10
0x38229  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3822e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x38233  ldarg.0
0x38234  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_fieldsLabel
0x38239  ldc.i4.s 0x1E
0x3823b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x38240  ldarg.0
0x38241  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_columnsTableLayoutPanel
0x38246  ldc.i4.s 0xF
0x38248  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3824d  ldarg.0
0x3824e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_columnsTableLayoutPanel
0x38253  ldc.i4.2
0x38254  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::set_ColumnCount(int32)
0x38259  ldarg.0
0x3825a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_columnsTableLayoutPanel
0x3825f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x38264  ldc.i4.2
0x38265  ldc.r4   100.0
0x3826a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x3826f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x38274  pop
0x38275  ldarg.0
0x38276  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSelectPanel::_columnsTableLayoutPanel
0x3827b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x38280  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor()
0x38285  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x3828a  pop
0x3828b  ldarg.0
  ... truncated ...
```
