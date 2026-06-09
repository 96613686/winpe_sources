# StyleEditorForm::InitializeComponent

- ea: `0x11f6c0`
- end: `0x120755`
- name: `StyleEditorForm::InitializeComponent`
- size: `4245`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x11f430`

## callees

- `0x8f6c0`
- `0x8f730`
- `0x8f740`
- `0x8f780`
- `0x11f3f0`
- `0x11f6c0`

## string_xrefs

- `0x11fa08`: `removeButton`
- `0x11fa4c`: `removeButton`
- `0x11f8b6`: `addRemoveInsertTableLayoutPanel`
- `0x11f976`: `addRemoveInsertTableLayoutPanel`
- `0x11febf`: `columnsOrRowsComboBox`
- `0x11ff2d`: `columnsOrRowsComboBox`
- `0x11fef5`: `columnsOrRowsComboBox.Items`
- `0x11ff03`: `columnsOrRowsComboBox.Items1`
- `0x1201dc`: `helperLinkLabel1`
- `0x120200`: `helperLinkLabel1`
- `0x120229`: `helperLinkLabel2`
- `0x12024d`: `helperLinkLabel2`

## pseudocode

```c

```

## disassembly

```asm
0x11f6c0  ldtoken  System.Windows.Forms.Design.StyleCollectionEditor
0x11f6c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11f6ca  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x11f6cf  stloc.0
0x11f6d0  ldarg.0
0x11f6d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x11f6d6  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f6db  ldarg.0
0x11f6dc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x11f6e1  stfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::addButton
0x11f6e6  ldarg.0
0x11f6e7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x11f6ec  stfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::removeButton
0x11f6f1  ldarg.0
0x11f6f2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x11f6f7  stfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::insertButton
0x11f6fc  ldarg.0
0x11f6fd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x11f702  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::okCancelTableLayoutPanel
0x11f707  ldarg.0
0x11f708  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x11f70d  stfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::okButton
0x11f712  ldarg.0
0x11f713  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x11f718  stfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::cancelButton
0x11f71d  ldarg.0
0x11f71e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x11f723  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::overarchingTableLayoutPanel
0x11f728  ldarg.0
0x11f729  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x11f72e  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::showTableLayoutPanel
0x11f733  ldarg.0
0x11f734  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x11f739  stfld    class [System.Windows.Forms]System.Windows.Forms.Label StyleEditorForm::memberTypeLabel
0x11f73e  ldarg.0
0x11f73f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ComboBox::.ctor()
0x11f744  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox StyleEditorForm::columnsOrRowsComboBox
0x11f749  ldarg.0
0x11f74a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListView::.ctor()
0x11f74f  stfld    class [System.Windows.Forms]System.Windows.Forms.ListView StyleEditorForm::columnsAndRowsListView
0x11f754  ldarg.0
0x11f755  ldloc.0
0x11f756  ldstr    aColumnsandrows// "columnsAndRowsListView.Columns"
0x11f75b  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x11f760  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor(string)
0x11f765  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader StyleEditorForm::membersColumnHeader
0x11f76a  ldarg.0
0x11f76b  ldloc.0
0x11f76c  ldstr    aColumnsandrows_0// "columnsAndRowsListView.Columns1"
0x11f771  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x11f776  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor(string)
0x11f77b  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader StyleEditorForm::sizeTypeColumnHeader
0x11f780  ldarg.0
0x11f781  ldloc.0
0x11f782  ldstr    aColumnsandrows_1// "columnsAndRowsListView.Columns2"
0x11f787  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x11f78c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnHeader::.ctor(string)
0x11f791  stfld    class [System.Windows.Forms]System.Windows.Forms.ColumnHeader StyleEditorForm::valueColumnHeader
0x11f796  ldarg.0
0x11f797  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x11f79c  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::helperTextTableLayoutPanel
0x11f7a1  ldarg.0
0x11f7a2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x11f7a7  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox StyleEditorForm::infoPictureBox2
0x11f7ac  ldarg.0
0x11f7ad  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x11f7b2  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox StyleEditorForm::infoPictureBox1
0x11f7b7  ldarg.0
0x11f7b8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x11f7bd  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel StyleEditorForm::helperLinkLabel1
0x11f7c2  ldarg.0
0x11f7c3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x11f7c8  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel StyleEditorForm::helperLinkLabel2
0x11f7cd  ldarg.0
0x11f7ce  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x11f7d3  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox StyleEditorForm::sizeTypeGroupBox
0x11f7d8  ldarg.0
0x11f7d9  newobj   instance void NavigationalTableLayoutPanel::.ctor()
0x11f7de  stfld    class NavigationalTableLayoutPanel StyleEditorForm::sizeTypeTableLayoutPanel
0x11f7e3  ldarg.0
0x11f7e4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.NumericUpDown::.ctor()
0x11f7e9  stfld    class [System.Windows.Forms]System.Windows.Forms.NumericUpDown StyleEditorForm::absoluteNumericUpDown
0x11f7ee  ldarg.0
0x11f7ef  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x11f7f4  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton StyleEditorForm::absoluteRadioButton
0x11f7f9  ldarg.0
0x11f7fa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x11f7ff  stfld    class [System.Windows.Forms]System.Windows.Forms.Label StyleEditorForm::pixelsLabel
0x11f804  ldarg.0
0x11f805  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x11f80a  stfld    class [System.Windows.Forms]System.Windows.Forms.Label StyleEditorForm::percentLabel
0x11f80f  ldarg.0
0x11f810  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x11f815  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton StyleEditorForm::percentRadioButton
0x11f81a  ldarg.0
0x11f81b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RadioButton::.ctor()
0x11f820  stfld    class [System.Windows.Forms]System.Windows.Forms.RadioButton StyleEditorForm::autoSizedRadioButton
0x11f825  ldarg.0
0x11f826  newobj   instance void [System.Windows.Forms]System.Windows.Forms.NumericUpDown::.ctor()
0x11f82b  stfld    class [System.Windows.Forms]System.Windows.Forms.NumericUpDown StyleEditorForm::percentNumericUpDown
0x11f830  ldarg.0
0x11f831  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f836  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x11f83b  ldarg.0
0x11f83c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::okCancelTableLayoutPanel
0x11f841  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x11f846  ldarg.0
0x11f847  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::overarchingTableLayoutPanel
0x11f84c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x11f851  ldarg.0
0x11f852  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::showTableLayoutPanel
0x11f857  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x11f85c  ldarg.0
0x11f85d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::helperTextTableLayoutPanel
0x11f862  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x11f867  ldarg.0
0x11f868  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox StyleEditorForm::infoPictureBox2
0x11f86d  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x11f872  ldarg.0
0x11f873  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox StyleEditorForm::infoPictureBox1
0x11f878  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x11f87d  ldarg.0
0x11f87e  ldfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox StyleEditorForm::sizeTypeGroupBox
0x11f883  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x11f888  ldarg.0
0x11f889  ldfld    class NavigationalTableLayoutPanel StyleEditorForm::sizeTypeTableLayoutPanel
0x11f88e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x11f893  ldarg.0
0x11f894  ldfld    class [System.Windows.Forms]System.Windows.Forms.NumericUpDown StyleEditorForm::absoluteNumericUpDown
0x11f899  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x11f89e  ldarg.0
0x11f89f  ldfld    class [System.Windows.Forms]System.Windows.Forms.NumericUpDown StyleEditorForm::percentNumericUpDown
0x11f8a4  callvirt instance void [System]System.ComponentModel.ISupportInitialize::BeginInit()
0x11f8a9  ldarg.0
0x11f8aa  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x11f8af  ldloc.0
0x11f8b0  ldarg.0
0x11f8b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f8b6  ldstr    aAddremoveinser// "addRemoveInsertTableLayoutPanel"
0x11f8bb  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x11f8c0  ldarg.0
0x11f8c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f8c6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x11f8cb  ldc.i4.2
0x11f8cc  ldc.r4   33.0
0x11f8d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x11f8d6  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x11f8db  pop
0x11f8dc  ldarg.0
0x11f8dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f8e2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x11f8e7  ldc.i4.2
0x11f8e8  ldc.r4   33.0
0x11f8ed  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x11f8f2  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x11f8f7  pop
0x11f8f8  ldarg.0
0x11f8f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f8fe  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x11f903  ldc.i4.2
0x11f904  ldc.r4   33.0
0x11f909  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x11f90e  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x11f913  pop
0x11f914  ldarg.0
0x11f915  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f91a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x11f91f  ldarg.0
0x11f920  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::addButton
0x11f925  ldc.i4.0
0x11f926  ldc.i4.0
0x11f927  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x11f92c  ldarg.0
0x11f92d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f932  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x11f937  ldarg.0
0x11f938  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::removeButton
0x11f93d  ldc.i4.1
0x11f93e  ldc.i4.0
0x11f93f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x11f944  ldarg.0
0x11f945  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f94a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x11f94f  ldarg.0
0x11f950  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::insertButton
0x11f955  ldc.i4.2
0x11f956  ldc.i4.0
0x11f957  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x11f95c  ldarg.0
0x11f95d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f962  ldc.i4.0
0x11f963  ldc.i4.3
0x11f964  ldc.i4.3
0x11f965  ldc.i4.3
0x11f966  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x11f96b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x11f970  ldarg.0
0x11f971  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f976  ldstr    aAddremoveinser// "addRemoveInsertTableLayoutPanel"
0x11f97b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x11f980  ldarg.0
0x11f981  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel StyleEditorForm::addRemoveInsertTableLayoutPanel
0x11f986  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x11f98b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x11f990  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x11f995  pop
0x11f996  ldloc.0
0x11f997  ldarg.0
0x11f998  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::addButton
0x11f99d  ldstr    aAddbutton_0// "addButton"
0x11f9a2  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x11f9a7  ldarg.0
0x11f9a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::addButton
0x11f9ad  ldc.i4.0
0x11f9ae  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_AutoSizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoSizeMode)
0x11f9b3  ldarg.0
0x11f9b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::addButton
0x11f9b9  ldc.i4.0
0x11f9ba  ldc.i4.0
0x11f9bb  ldc.i4.4
0x11f9bc  ldc.i4.0
0x11f9bd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x11f9c2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x11f9c7  ldarg.0
0x11f9c8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::addButton
0x11f9cd  ldc.i4.s 0x4B
0x11f9cf  ldc.i4.s 0x17
0x11f9d1  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x11f9d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x11f9db  ldarg.0
0x11f9dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::addButton
0x11f9e1  ldstr    aAddbutton_0// "addButton"
0x11f9e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x11f9eb  ldarg.0
0x11f9ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::addButton
0x11f9f1  ldc.i4.s 0xA
0x11f9f3  ldc.i4.0
0x11f9f4  ldc.i4.s 0xA
0x11f9f6  ldc.i4.0
0x11f9f7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x11f9fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Padding(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x11fa01  ldloc.0
0x11fa02  ldarg.0
0x11fa03  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::removeButton
0x11fa08  ldstr    aRemovebutton_0// "removeButton"
0x11fa0d  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x11fa12  ldarg.0
0x11fa13  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::removeButton
0x11fa18  ldc.i4.0
0x11fa19  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_AutoSizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoSizeMode)
0x11fa1e  ldarg.0
0x11fa1f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::removeButton
0x11fa24  ldc.i4.2
0x11fa25  ldc.i4.0
0x11fa26  ldc.i4.2
0x11fa27  ldc.i4.0
0x11fa28  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x11fa2d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x11fa32  ldarg.0
0x11fa33  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::removeButton
0x11fa38  ldc.i4.s 0x4B
0x11fa3a  ldc.i4.s 0x17
0x11fa3c  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x11fa41  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x11fa46  ldarg.0
0x11fa47  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::removeButton
0x11fa4c  ldstr    aRemovebutton_0// "removeButton"
0x11fa51  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x11fa56  ldarg.0
0x11fa57  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::removeButton
0x11fa5c  ldc.i4.s 0xA
0x11fa5e  ldc.i4.0
0x11fa5f  ldc.i4.s 0xA
0x11fa61  ldc.i4.0
0x11fa62  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x11fa67  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Padding(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x11fa6c  ldloc.0
0x11fa6d  ldarg.0
0x11fa6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::insertButton
0x11fa73  ldstr    aInsertbutton// "insertButton"
0x11fa78  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x11fa7d  ldarg.0
0x11fa7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::insertButton
0x11fa83  ldc.i4.0
0x11fa84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_AutoSizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoSizeMode)
0x11fa89  ldarg.0
0x11fa8a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::insertButton
0x11fa8f  ldc.i4.4
0x11fa90  ldc.i4.0
0x11fa91  ldc.i4.0
0x11fa92  ldc.i4.0
0x11fa93  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x11fa98  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x11fa9d  ldarg.0
0x11fa9e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button StyleEditorForm::insertButton
0x11faa3  ldc.i4.s 0x4B
0x11faa5  ldc.i4.s 0x17
0x11faa7  newobj   instance void [System.Drawing]System.Drawing.Size::.ctor(int32, int32)
0x11faac  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_MinimumSize(valuetype [System.Drawing]System.Drawing.Size)
0x11fab1  ldarg.0
  ... truncated ...
```
