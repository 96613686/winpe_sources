# System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::InitializeComponent

- ea: `0x3a8e0`
- end: `0x3b3ef`
- name: `System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::InitializeComponent`
- size: `2831`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3a5e0`

## callees

- `0x518a0`
- `0x51a90`

## string_xrefs

- `0x3abb4`: `_fieldComboBox1`
- `0x3ace9`: `_fieldComboBox2`
- `0x3ae95`: `_fieldComboBox3`
- `0x3b388`: `SqlDataSourceConfigureSortForm`

## pseudocode

```c

```

## disassembly

```asm
0x3a8e0  ldarg.0
0x3a8e1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x3a8e6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_helpLabel
0x3a8eb  ldarg.0
0x3a8ec  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x3a8f1  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_previewLabel
0x3a8f6  ldarg.0
0x3a8f7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x3a8fc  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_previewTextBox
0x3a901  ldarg.0
0x3a902  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x3a907  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3a90c  ldarg.0
0x3a90d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x3a912  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3a917  ldarg.0
0x3a918  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x3a91d  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel1
0x3a922  ldarg.0
0x3a923  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x3a928  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3a92d  ldarg.0
0x3a92e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x3a933  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_okButton
0x3a938  ldarg.0
0x3a939  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x3a93e  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_cancelButton
0x3a943  ldarg.0
0x3a944  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x3a949  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton2
0x3a94e  ldarg.0
0x3a94f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x3a954  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3a959  ldarg.0
0x3a95a  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x3a95f  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox2
0x3a964  ldarg.0
0x3a965  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x3a96a  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel2
0x3a96f  ldarg.0
0x3a970  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x3a975  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton3
0x3a97a  ldarg.0
0x3a97b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x3a980  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton3
0x3a985  ldarg.0
0x3a986  newobj   instance void System.Web.UI.Design.Util.AutoSizeComboBox::.ctor()
0x3a98b  stfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox3
0x3a990  ldarg.0
0x3a991  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0x3a996  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel3
0x3a99b  ldarg.0
0x3a99c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x3a9a1  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox1
0x3a9a6  ldarg.0
0x3a9a7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x3a9ac  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox2
0x3a9b1  ldarg.0
0x3a9b2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x3a9b7  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox3
0x3a9bc  ldarg.0
0x3a9bd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel1
0x3a9c2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3a9c7  ldarg.0
0x3a9c8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel2
0x3a9cd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3a9d2  ldarg.0
0x3a9d3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel3
0x3a9d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3a9dd  ldarg.0
0x3a9de  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox1
0x3a9e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3a9e8  ldarg.0
0x3a9e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox2
0x3a9ee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3a9f3  ldarg.0
0x3a9f4  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortByGroupBox3
0x3a9f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3a9fe  ldarg.0
0x3a9ff  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x3aa04  ldarg.0
0x3aa05  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_helpLabel
0x3aa0a  ldc.i4.s 0xD
0x3aa0c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3aa11  ldarg.0
0x3aa12  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_helpLabel
0x3aa17  ldc.i4.s 0xC
0x3aa19  ldc.i4.s 0xC
0x3aa1b  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3aa20  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3aa25  ldarg.0
0x3aa26  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_helpLabel
0x3aa2b  ldstr    aHelplabel// "_helpLabel"
0x3aa30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3aa35  ldarg.0
0x3aa36  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_helpLabel
0x3aa3b  ldc.i4   0x17E
0x3aa40  ldc.i4.s 0x10
0x3aa42  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3aa47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3aa4c  ldarg.0
0x3aa4d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_helpLabel
0x3aa52  ldc.i4.s 0xA
0x3aa54  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3aa59  ldarg.0
0x3aa5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3aa5f  ldc.i4.s 0xD
0x3aa61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3aa66  ldarg.0
0x3aa67  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3aa6c  ldc.i4.0
0x3aa6d  ldc.i4.0
0x3aa6e  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3aa73  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3aa78  ldarg.0
0x3aa79  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3aa7e  ldstr    aSortascendingr// "_sortAscendingRadioButton1"
0x3aa83  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3aa88  ldarg.0
0x3aa89  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3aa8e  ldc.i4   0xC8
0x3aa93  ldc.i4.s 0x12
0x3aa95  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3aa9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3aa9f  ldarg.0
0x3aaa0  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3aaa5  ldc.i4.s 0xA
0x3aaa7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3aaac  ldarg.0
0x3aaad  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3aab2  ldarg.0
0x3aab3  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::OnSortAscendingRadioButton1CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x3aab9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x3aabe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x3aac3  ldarg.0
0x3aac4  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3aac9  ldc.i4.s 0xD
0x3aacb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3aad0  ldarg.0
0x3aad1  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3aad6  ldc.i4.0
0x3aad7  ldc.i4.s 0x12
0x3aad9  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3aade  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3aae3  ldarg.0
0x3aae4  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3aae9  ldstr    aSortdescending// "_sortDescendingRadioButton1"
0x3aaee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3aaf3  ldarg.0
0x3aaf4  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3aaf9  ldc.i4   0xC8
0x3aafe  ldc.i4.s 0x12
0x3ab00  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3ab05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3ab0a  ldarg.0
0x3ab0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3ab10  ldc.i4.s 0x14
0x3ab12  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3ab17  ldarg.0
0x3ab18  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel1
0x3ab1d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3ab22  ldarg.0
0x3ab23  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton1
0x3ab28  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3ab2d  ldarg.0
0x3ab2e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel1
0x3ab33  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x3ab38  ldarg.0
0x3ab39  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton1
0x3ab3e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x3ab43  ldarg.0
0x3ab44  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel1
0x3ab49  ldc.i4   0xA9
0x3ab4e  ldc.i4.s 0xC
0x3ab50  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3ab55  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3ab5a  ldarg.0
0x3ab5b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel1
0x3ab60  ldstr    aSortdirectionp// "_sortDirectionPanel1"
0x3ab65  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3ab6a  ldarg.0
0x3ab6b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel1
0x3ab70  ldc.i4   0xC8
0x3ab75  ldc.i4.s 0x26
0x3ab77  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3ab7c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3ab81  ldarg.0
0x3ab82  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDirectionPanel1
0x3ab87  ldc.i4.s 0x14
0x3ab89  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3ab8e  ldarg.0
0x3ab8f  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3ab94  ldc.i4.2
0x3ab95  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x3ab9a  ldarg.0
0x3ab9b  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3aba0  ldc.i4.s 9
0x3aba2  ldc.i4.s 0x14
0x3aba4  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3aba9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3abae  ldarg.0
0x3abaf  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3abb4  ldstr    aFieldcombobox1// "_fieldComboBox1"
0x3abb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3abbe  ldarg.0
0x3abbf  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3abc4  ldc.i4   0x99
0x3abc9  ldc.i4.s 0x15
0x3abcb  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3abd0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3abd5  ldarg.0
0x3abd6  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3abdb  ldc.i4.1
0x3abdc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_Sorted(bool)
0x3abe1  ldarg.0
0x3abe2  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3abe7  ldc.i4.s 0xA
0x3abe9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3abee  ldarg.0
0x3abef  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox1
0x3abf4  ldarg.0
0x3abf5  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::OnFieldComboBox1SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0x3abfb  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x3ac00  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0x3ac05  ldarg.0
0x3ac06  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton2
0x3ac0b  ldc.i4.s 0xD
0x3ac0d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3ac12  ldarg.0
0x3ac13  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton2
0x3ac18  ldc.i4.0
0x3ac19  ldc.i4.s 0x12
0x3ac1b  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3ac20  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3ac25  ldarg.0
0x3ac26  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton2
0x3ac2b  ldstr    aSortdescending_0// "_sortDescendingRadioButton2"
0x3ac30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3ac35  ldarg.0
0x3ac36  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton2
0x3ac3b  ldc.i4   0xC8
0x3ac40  ldc.i4.s 0x12
0x3ac42  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3ac47  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3ac4c  ldarg.0
0x3ac4d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortDescendingRadioButton2
0x3ac52  ldc.i4.s 0x14
0x3ac54  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3ac59  ldarg.0
0x3ac5a  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3ac5f  ldc.i4.s 0xD
0x3ac61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x3ac66  ldarg.0
0x3ac67  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3ac6c  ldc.i4.0
0x3ac6d  ldc.i4.0
0x3ac6e  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3ac73  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3ac78  ldarg.0
0x3ac79  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3ac7e  ldstr    aSortascendingr_0// "_sortAscendingRadioButton2"
0x3ac83  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3ac88  ldarg.0
0x3ac89  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3ac8e  ldc.i4   0xC8
0x3ac93  ldc.i4.s 0x12
0x3ac95  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3ac9a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3ac9f  ldarg.0
0x3aca0  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3aca5  ldc.i4.s 0xA
0x3aca7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x3acac  ldarg.0
0x3acad  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_sortAscendingRadioButton2
0x3acb2  ldarg.0
0x3acb3  ldftn    instance void System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::OnSortAscendingRadioButton2CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0x3acb9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x3acbe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0x3acc3  ldarg.0
0x3acc4  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox2
0x3acc9  ldc.i4.2
0x3acca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::set_DropDownStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ComboBoxStyle)
0x3accf  ldarg.0
0x3acd0  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox2
0x3acd5  ldc.i4.s 9
0x3acd7  ldc.i4.s 0x14
0x3acd9  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x3acde  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x3ace3  ldarg.0
0x3ace4  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox2
0x3ace9  ldstr    aFieldcombobox2// "_fieldComboBox2"
0x3acee  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x3acf3  ldarg.0
0x3acf4  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox2
0x3acf9  ldc.i4   0x99
0x3acfe  ldc.i4.s 0x15
0x3ad00  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x3ad05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x3ad0a  ldarg.0
0x3ad0b  ldfld    class System.Web.UI.Design.Util.AutoSizeComboBox System.Web.UI.Design.WebControls.SqlDataSourceConfigureSortForm::_fieldComboBox2
  ... truncated ...
```
