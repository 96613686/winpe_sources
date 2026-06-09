# System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::InitializeComponent

- ea: `0xa9f00`
- end: `0xaa787`
- name: `System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::InitializeComponent`
- size: `2183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa94b0`

## callees

- `0xe3d40`

## string_xrefs

- `0xaa035`: `deleteButton`
- `0xaa059`: `deleteButton`
- `0xaa097`: `moveDown`
- `0xaa0bc`: `moveDown`
- `0xaa0e4`: `moveUp`
- `0xaa109`: `moveUp`
- `0xaa362`: `addRemoveTableLayoutPanel`
- `0xaa3ee`: `addRemoveTableLayoutPanel`

## pseudocode

```c

```

## disassembly

```asm
0xa9f00  ldtoken  System.Windows.Forms.Design.DataGridViewColumnCollectionDialog
0xa9f05  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa9f0a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0xa9f0f  stloc.0
0xa9f10  ldarg.0
0xa9f11  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa9f16  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addButton
0xa9f1b  ldarg.0
0xa9f1c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa9f21  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::deleteButton
0xa9f26  ldarg.0
0xa9f27  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa9f2c  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveDown
0xa9f31  ldarg.0
0xa9f32  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa9f37  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveUp
0xa9f3c  ldarg.0
0xa9f3d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ListBox::.ctor()
0xa9f42  stfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xa9f47  ldarg.0
0xa9f48  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0xa9f4d  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xa9f52  ldarg.0
0xa9f53  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0xa9f58  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addRemoveTableLayoutPanel
0xa9f5d  ldarg.0
0xa9f5e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xa9f63  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumnsLabel
0xa9f68  ldarg.0
0xa9f69  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xa9f6e  stfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::propertyGridLabel
0xa9f73  ldarg.0
0xa9f74  ldarg.0
0xa9f75  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::serviceProvider
0xa9f7a  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0xa9f7f  stfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::propertyGrid1
0xa9f84  ldarg.0
0xa9f85  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0xa9f8a  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::okCancelTableLayoutPanel
0xa9f8f  ldarg.0
0xa9f90  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa9f95  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::cancelButton
0xa9f9a  ldarg.0
0xa9f9b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa9fa0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::okButton
0xa9fa5  ldarg.0
0xa9fa6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xa9fab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa9fb0  ldarg.0
0xa9fb1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addRemoveTableLayoutPanel
0xa9fb6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa9fbb  ldarg.0
0xa9fbc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::okCancelTableLayoutPanel
0xa9fc1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa9fc6  ldarg.0
0xa9fc7  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa9fcc  ldloc.0
0xa9fcd  ldarg.0
0xa9fce  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addButton
0xa9fd3  ldstr    aAddbutton_0// "addButton"
0xa9fd8  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0xa9fdd  ldarg.0
0xa9fde  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addButton
0xa9fe3  ldc.i4.0
0xa9fe4  ldc.i4.0
0xa9fe5  ldc.i4.3
0xa9fe6  ldc.i4.0
0xa9fe7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0xa9fec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xa9ff1  ldarg.0
0xa9ff2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addButton
0xa9ff7  ldstr    aAddbutton_0// "addButton"
0xa9ffc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xaa001  ldarg.0
0xaa002  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addButton
0xaa007  ldc.i4.s 0xA
0xaa009  ldc.i4.0
0xaa00a  ldc.i4.s 0xA
0xaa00c  ldc.i4.0
0xaa00d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0xaa012  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Padding(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xaa017  ldarg.0
0xaa018  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addButton
0xaa01d  ldarg.0
0xaa01e  ldftn    instance void System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addButton_Click(object sender, class [mscorlib]System.EventArgs e)
0xaa024  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xaa029  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0xaa02e  ldloc.0
0xaa02f  ldarg.0
0xaa030  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::deleteButton
0xaa035  ldstr    aDeletebutton// "deleteButton"
0xaa03a  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0xaa03f  ldarg.0
0xaa040  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::deleteButton
0xaa045  ldc.i4.3
0xaa046  ldc.i4.0
0xaa047  ldc.i4.0
0xaa048  ldc.i4.0
0xaa049  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0xaa04e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xaa053  ldarg.0
0xaa054  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::deleteButton
0xaa059  ldstr    aDeletebutton// "deleteButton"
0xaa05e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xaa063  ldarg.0
0xaa064  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::deleteButton
0xaa069  ldc.i4.s 0xA
0xaa06b  ldc.i4.0
0xaa06c  ldc.i4.s 0xA
0xaa06e  ldc.i4.0
0xaa06f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0xaa074  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Padding(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xaa079  ldarg.0
0xaa07a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::deleteButton
0xaa07f  ldarg.0
0xaa080  ldftn    instance void System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::deleteButton_Click(object sender, class [mscorlib]System.EventArgs e)
0xaa086  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xaa08b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0xaa090  ldloc.0
0xaa091  ldarg.0
0xaa092  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveDown
0xaa097  ldstr    aMovedown// "moveDown"
0xaa09c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0xaa0a1  ldarg.0
0xaa0a2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveDown
0xaa0a7  ldc.i4.0
0xaa0a8  ldc.i4.1
0xaa0a9  ldc.i4.s 0x12
0xaa0ab  ldc.i4.0
0xaa0ac  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0xaa0b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xaa0b6  ldarg.0
0xaa0b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveDown
0xaa0bc  ldstr    aMovedown// "moveDown"
0xaa0c1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xaa0c6  ldarg.0
0xaa0c7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveDown
0xaa0cc  ldarg.0
0xaa0cd  ldftn    instance void System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveDown_Click(object sender, class [mscorlib]System.EventArgs e)
0xaa0d3  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xaa0d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0xaa0dd  ldloc.0
0xaa0de  ldarg.0
0xaa0df  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveUp
0xaa0e4  ldstr    aMoveup// "moveUp"
0xaa0e9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0xaa0ee  ldarg.0
0xaa0ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveUp
0xaa0f4  ldc.i4.0
0xaa0f5  ldc.i4.0
0xaa0f6  ldc.i4.s 0x12
0xaa0f8  ldc.i4.1
0xaa0f9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0xaa0fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xaa103  ldarg.0
0xaa104  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveUp
0xaa109  ldstr    aMoveup// "moveUp"
0xaa10e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xaa113  ldarg.0
0xaa114  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveUp
0xaa119  ldarg.0
0xaa11a  ldftn    instance void System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveUp_Click(object sender, class [mscorlib]System.EventArgs e)
0xaa120  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xaa125  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0xaa12a  ldloc.0
0xaa12b  ldarg.0
0xaa12c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa131  ldstr    aSelectedcolumn_1// "selectedColumns"
0xaa136  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0xaa13b  ldarg.0
0xaa13c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa141  ldc.i4.1
0xaa142  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::set_DrawMode(valuetype [System.Windows.Forms]System.Windows.Forms.DrawMode)
0xaa147  ldarg.0
0xaa148  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa14d  ldc.i4.0
0xaa14e  ldc.i4.2
0xaa14f  ldc.i4.3
0xaa150  ldc.i4.3
0xaa151  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0xaa156  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xaa15b  ldarg.0
0xaa15c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa161  ldstr    aSelectedcolumn_1// "selectedColumns"
0xaa166  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xaa16b  ldarg.0
0xaa16c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa171  ldarg.0
0xaa172  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa177  ldc.i4.2
0xaa178  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::SetRowSpan(class [System.Windows.Forms]System.Windows.Forms.Control, int32)
0xaa17d  ldarg.0
0xaa17e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa183  ldarg.0
0xaa184  ldftn    instance void System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns_SelectedIndexChanged(object sender, class [mscorlib]System.EventArgs e)
0xaa18a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xaa18f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::add_SelectedIndexChanged(class [mscorlib]System.EventHandler)
0xaa194  ldarg.0
0xaa195  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa19a  ldarg.0
0xaa19b  ldftn    instance void System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns_KeyPress(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyPressEventArgs e)
0xaa1a1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler::.ctor(object, native int)
0xaa1a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyPress(class [System.Windows.Forms]System.Windows.Forms.KeyPressEventHandler)
0xaa1ab  ldarg.0
0xaa1ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa1b1  ldarg.0
0xaa1b2  ldftn    instance void System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns_DrawItem(object sender, class [System.Windows.Forms]System.Windows.Forms.DrawItemEventArgs e)
0xaa1b8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.DrawItemEventHandler::.ctor(object, native int)
0xaa1bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ListBox::add_DrawItem(class [System.Windows.Forms]System.Windows.Forms.DrawItemEventHandler)
0xaa1c2  ldarg.0
0xaa1c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa1c8  ldarg.0
0xaa1c9  ldftn    instance void System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns_KeyUp(object sender, class [System.Windows.Forms]System.Windows.Forms.KeyEventArgs e)
0xaa1cf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.KeyEventHandler::.ctor(object, native int)
0xaa1d4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_KeyUp(class [System.Windows.Forms]System.Windows.Forms.KeyEventHandler)
0xaa1d9  ldloc.0
0xaa1da  ldarg.0
0xaa1db  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa1e0  ldstr    aOverarchingtab// "overarchingTableLayoutPanel"
0xaa1e5  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0xaa1ea  ldarg.0
0xaa1eb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa1f0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xaa1f5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor()
0xaa1fa  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0xaa1ff  pop
0xaa200  ldarg.0
0xaa201  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa206  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xaa20b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor()
0xaa210  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0xaa215  pop
0xaa216  ldarg.0
0xaa217  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa21c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xaa221  ldc.i4.2
0xaa222  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType)
0xaa227  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0xaa22c  pop
0xaa22d  ldarg.0
0xaa22e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa233  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xaa238  ldarg.0
0xaa239  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::addRemoveTableLayoutPanel
0xaa23e  ldc.i4.0
0xaa23f  ldc.i4.3
0xaa240  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xaa245  ldarg.0
0xaa246  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa24b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xaa250  ldarg.0
0xaa251  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveUp
0xaa256  ldc.i4.1
0xaa257  ldc.i4.1
0xaa258  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xaa25d  ldarg.0
0xaa25e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa263  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xaa268  ldarg.0
0xaa269  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumnsLabel
0xaa26e  ldc.i4.0
0xaa26f  ldc.i4.0
0xaa270  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xaa275  ldarg.0
0xaa276  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa27b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xaa280  ldarg.0
0xaa281  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::moveDown
0xaa286  ldc.i4.1
0xaa287  ldc.i4.2
0xaa288  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xaa28d  ldarg.0
0xaa28e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa293  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xaa298  ldarg.0
0xaa299  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::propertyGridLabel
0xaa29e  ldc.i4.2
0xaa29f  ldc.i4.0
0xaa2a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xaa2a5  ldarg.0
0xaa2a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa2ab  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xaa2b0  ldarg.0
0xaa2b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ListBox System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::selectedColumns
0xaa2b6  ldc.i4.0
0xaa2b7  ldc.i4.1
0xaa2b8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xaa2bd  ldarg.0
0xaa2be  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa2c3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xaa2c8  ldarg.0
0xaa2c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.PropertyGrid System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::propertyGrid1
0xaa2ce  ldc.i4.2
0xaa2cf  ldc.i4.1
0xaa2d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0xaa2d5  ldarg.0
0xaa2d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::overarchingTableLayoutPanel
0xaa2db  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0xaa2e0  ldarg.0
0xaa2e1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.DataGridViewColumnCollectionDialog::okCancelTableLayoutPanel
  ... truncated ...
```
