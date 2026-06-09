# System.Windows.Forms.Design.DataGridViewAddColumnDialog::InitializeComponent

- ea: `0xa7170`
- end: `0xa7c2c`
- name: `System.Windows.Forms.Design.DataGridViewAddColumnDialog::InitializeComponent`
- size: `2748`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa6cf0`

## string_xrefs

- `0xa772a`: `readOnlyCheckBox`
- `0xa774b`: `readOnlyCheckBox`
- `0xa7a60`: `columnTypesCombo`
- `0xa7a99`: `columnTypesCombo`

## pseudocode

```c

```

## disassembly

```asm
0xa7170  ldtoken  System.Windows.Forms.Design.DataGridViewAddColumnDialog
0xa7175  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa717a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0xa717f  stloc.0
0xa7180  ldarg.0
0xa7181  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0xa7186  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton
0xa718b  ldarg.0
0xa718c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0xa7191  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7196  ldarg.0
0xa7197  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0xa719c  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::checkBoxesTableLayoutPanel
0xa71a1  ldarg.0
0xa71a2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xa71a7  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::frozenCheckBox
0xa71ac  ldarg.0
0xa71ad  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xa71b2  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::visibleCheckBox
0xa71b7  ldarg.0
0xa71b8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0xa71bd  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::readOnlyCheckBox
0xa71c2  ldarg.0
0xa71c3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0xa71c8  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::okCancelTableLayoutPanel
0xa71cd  ldarg.0
0xa71ce  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa71d3  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewAddColumnDialog::addButton
0xa71d8  ldarg.0
0xa71d9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa71de  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewAddColumnDialog::cancelButton
0xa71e3  ldarg.0
0xa71e4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xa71e9  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewAddColumnDialog::columnInDataSourceLabel
0xa71ee  ldarg.0
0xa71ef  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListBox::.ctor()
0xa71f4  stfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataColumns
0xa71f9  ldarg.0
0xa71fa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0xa71ff  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::unboundColumnRadioButton
0xa7204  ldarg.0
0xa7205  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xa720a  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewAddColumnDialog::nameLabel
0xa720f  ldarg.0
0xa7210  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xa7215  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::nameTextBox
0xa721a  ldarg.0
0xa721b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xa7220  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewAddColumnDialog::typeLabel
0xa7225  ldarg.0
0xa7226  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0xa722b  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::columnTypesCombo
0xa7230  ldarg.0
0xa7231  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xa7236  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewAddColumnDialog::headerTextLabel
0xa723b  ldarg.0
0xa723c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xa7241  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::headerTextBox
0xa7246  ldarg.0
0xa7247  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa724c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa7251  ldarg.0
0xa7252  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::checkBoxesTableLayoutPanel
0xa7257  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa725c  ldarg.0
0xa725d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::okCancelTableLayoutPanel
0xa7262  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa7267  ldarg.0
0xa7268  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa726d  ldloc.0
0xa726e  ldarg.0
0xa726f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton
0xa7274  ldstr    aDataboundcolum// "dataBoundColumnRadioButton"
0xa7279  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0xa727e  ldarg.0
0xa727f  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton
0xa7284  ldc.i4.1
0xa7285  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::set_Checked(bool)
0xa728a  ldarg.0
0xa728b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7290  ldarg.0
0xa7291  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton
0xa7296  ldc.i4.3
0xa7297  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetColumnSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0xa729c  ldarg.0
0xa729d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton
0xa72a2  ldc.i4.0
0xa72a3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32)
0xa72a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xa72ad  ldarg.0
0xa72ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton
0xa72b3  ldstr    aDataboundcolum// "dataBoundColumnRadioButton"
0xa72b8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa72bd  ldarg.0
0xa72be  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton
0xa72c3  ldarg.0
0xa72c4  ldftn    instance void System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton_CheckedChanged(object sender, class [mscorlib]System.EventArgs e)
0xa72ca  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa72cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::add_CheckedChanged(class [mscorlib]System.EventHandler)
0xa72d4  ldloc.0
0xa72d5  ldarg.0
0xa72d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa72db  ldstr    aOverarchingtab// "overarchingTableLayoutPanel"
0xa72e0  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0xa72e5  ldarg.0
0xa72e6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa72eb  ldc.i4.0
0xa72ec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Panel::set_AutoSizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoSizeMode)
0xa72f1  ldarg.0
0xa72f2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa72f7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xa72fc  ldc.i4.1
0xa72fd  ldc.r4   14.0
0xa7302  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0xa7307  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0xa730c  pop
0xa730d  ldarg.0
0xa730e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7313  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xa7318  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor()
0xa731d  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0xa7322  pop
0xa7323  ldarg.0
0xa7324  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7329  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xa732e  ldc.i4.1
0xa732f  ldc.r4   250.0
0xa7334  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0xa7339  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0xa733e  pop
0xa733f  ldarg.0
0xa7340  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7345  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa734a  ldarg.0
0xa734b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::checkBoxesTableLayoutPanel
0xa7350  ldc.i4.0
0xa7351  ldc.i4.s 0xA
0xa7353  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa7358  ldarg.0
0xa7359  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa735e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa7363  ldarg.0
0xa7364  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::okCancelTableLayoutPanel
0xa7369  ldc.i4.2
0xa736a  ldc.i4.s 0xB
0xa736c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa7371  ldarg.0
0xa7372  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7377  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa737c  ldarg.0
0xa737d  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataBoundColumnRadioButton
0xa7382  ldc.i4.0
0xa7383  ldc.i4.0
0xa7384  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa7389  ldarg.0
0xa738a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa738f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa7394  ldarg.0
0xa7395  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewAddColumnDialog::columnInDataSourceLabel
0xa739a  ldc.i4.1
0xa739b  ldc.i4.1
0xa739c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa73a1  ldarg.0
0xa73a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa73a7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa73ac  ldarg.0
0xa73ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::dataColumns
0xa73b2  ldc.i4.1
0xa73b3  ldc.i4.2
0xa73b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa73b9  ldarg.0
0xa73ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa73bf  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa73c4  ldarg.0
0xa73c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton System.Windows.Forms.Design.DataGridViewAddColumnDialog::unboundColumnRadioButton
0xa73ca  ldc.i4.0
0xa73cb  ldc.i4.4
0xa73cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa73d1  ldarg.0
0xa73d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa73d7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa73dc  ldarg.0
0xa73dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewAddColumnDialog::nameLabel
0xa73e2  ldc.i4.1
0xa73e3  ldc.i4.5
0xa73e4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa73e9  ldarg.0
0xa73ea  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa73ef  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa73f4  ldarg.0
0xa73f5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::nameTextBox
0xa73fa  ldc.i4.2
0xa73fb  ldc.i4.5
0xa73fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa7401  ldarg.0
0xa7402  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7407  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa740c  ldarg.0
0xa740d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewAddColumnDialog::typeLabel
0xa7412  ldc.i4.1
0xa7413  ldc.i4.7
0xa7414  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa7419  ldarg.0
0xa741a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa741f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa7424  ldarg.0
0xa7425  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::columnTypesCombo
0xa742a  ldc.i4.2
0xa742b  ldc.i4.7
0xa742c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa7431  ldarg.0
0xa7432  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7437  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa743c  ldarg.0
0xa743d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewAddColumnDialog::headerTextLabel
0xa7442  ldc.i4.1
0xa7443  ldc.i4.s 9
0xa7445  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa744a  ldarg.0
0xa744b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7450  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xa7455  ldarg.0
0xa7456  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox System.Windows.Forms.Design.DataGridViewAddColumnDialog::headerTextBox
0xa745b  ldc.i4.2
0xa745c  ldc.i4.s 9
0xa745e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xa7463  ldarg.0
0xa7464  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7469  ldc.i4.s 0xC
0xa746b  ldc.i4.s 0xC
0xa746d  ldc.i4.s 0xC
0xa746f  ldc.i4.s 0xD
0xa7471  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0xa7476  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xa747b  ldarg.0
0xa747c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7481  ldstr    aOverarchingtab// "overarchingTableLayoutPanel"
0xa7486  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa748b  ldarg.0
0xa748c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7491  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xa7496  ldc.i4.1
0xa7497  ldc.r4   22.0
0xa749c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0xa74a1  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0xa74a6  pop
0xa74a7  ldarg.0
0xa74a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa74ad  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xa74b2  ldc.i4.1
0xa74b3  ldc.r4   16.0
0xa74b8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0xa74bd  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0xa74c2  pop
0xa74c3  ldarg.0
0xa74c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa74c9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xa74ce  ldc.i4.1
0xa74cf  ldc.r4   91.0
0xa74d4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0xa74d9  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0xa74de  pop
0xa74df  ldarg.0
0xa74e0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa74e5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xa74ea  ldc.i4.1
0xa74eb  ldc.r4   12.0
0xa74f0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0xa74f5  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0xa74fa  pop
0xa74fb  ldarg.0
0xa74fc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7501  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xa7506  ldc.i4.1
0xa7507  ldc.r4   22.0
0xa750c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0xa7511  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0xa7516  pop
0xa7517  ldarg.0
0xa7518  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa751d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xa7522  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0xa7527  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0xa752c  pop
0xa752d  ldarg.0
0xa752e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa7533  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xa7538  ldc.i4.1
0xa7539  ldc.r4   4.0
0xa753e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0xa7543  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0xa7548  pop
0xa7549  ldarg.0
0xa754a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
0xa754f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xa7554  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0xa7559  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0xa755e  pop
0xa755f  ldarg.0
0xa7560  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewAddColumnDialog::overarchingTableLayoutPanel
  ... truncated ...
```
