# TreeNodeCollectionForm::InitializeComponent

- ea: `0x124dc0`
- end: `0x1255bb`
- name: `TreeNodeCollectionForm::InitializeComponent`
- size: `2043`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1249f0`

## callees

- `0xe3d40`
- `0x1060b0`

## string_xrefs

- `0x125106`: `btnDelete`
- `0x12512a`: `btnDelete`
- `0x12513b`: `moveDownButton`
- `0x12515f`: `moveDownButton`
- `0x125170`: `moveUpButton`
- `0x125194`: `moveUpButton`

## pseudocode

```c

```

## disassembly

```asm
0x124dc0  ldtoken  System.Windows.Forms.Design.TreeNodeCollectionEditor
0x124dc5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x124dca  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x124dcf  stloc.0
0x124dd0  ldarg.0
0x124dd1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x124dd6  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124ddb  ldarg.0
0x124ddc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x124de1  stfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::okButton
0x124de6  ldarg.0
0x124de7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x124dec  stfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnCancel
0x124df1  ldarg.0
0x124df2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x124df7  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x124dfc  ldarg.0
0x124dfd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x124e02  stfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddRoot
0x124e07  ldarg.0
0x124e08  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x124e0d  stfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddChild
0x124e12  ldarg.0
0x124e13  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x124e18  stfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnDelete
0x124e1d  ldarg.0
0x124e1e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x124e23  stfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::moveDownButton
0x124e28  ldarg.0
0x124e29  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x124e2e  stfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::moveUpButton
0x124e33  ldarg.0
0x124e34  ldarg.0
0x124e35  call     instance class [System]System.ComponentModel.ITypeDescriptorContext CollectionForm::get_Context()
0x124e3a  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x124e3f  stfld    class System.Windows.Forms.Design.VsPropertyGrid TreeNodeCollectionForm::propertyGrid1
0x124e44  ldarg.0
0x124e45  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x124e4a  stfld    class [System.Windows.Forms]System.Windows.Forms.Label TreeNodeCollectionForm::label2
0x124e4f  ldarg.0
0x124e50  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeView::.ctor()
0x124e55  stfld    class [System.Windows.Forms]System.Windows.Forms.TreeView TreeNodeCollectionForm::treeView1
0x124e5a  ldarg.0
0x124e5b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x124e60  stfld    class [System.Windows.Forms]System.Windows.Forms.Label TreeNodeCollectionForm::label1
0x124e65  ldarg.0
0x124e66  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x124e6b  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::overarchingTableLayoutPanel
0x124e70  ldarg.0
0x124e71  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x124e76  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::navigationButtonsTableLayoutPanel
0x124e7b  ldarg.0
0x124e7c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124e81  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x124e86  ldarg.0
0x124e87  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x124e8c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x124e91  ldarg.0
0x124e92  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::overarchingTableLayoutPanel
0x124e97  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x124e9c  ldarg.0
0x124e9d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::navigationButtonsTableLayoutPanel
0x124ea2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x124ea7  ldarg.0
0x124ea8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x124ead  ldloc.0
0x124eae  ldarg.0
0x124eaf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124eb4  ldstr    aOkcancelpanel// "okCancelPanel"
0x124eb9  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x124ebe  ldarg.0
0x124ebf  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124ec4  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x124ec9  ldc.i4.2
0x124eca  ldc.r4   50.0
0x124ecf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x124ed4  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x124ed9  pop
0x124eda  ldarg.0
0x124edb  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124ee0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x124ee5  ldc.i4.2
0x124ee6  ldc.r4   50.0
0x124eeb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x124ef0  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x124ef5  pop
0x124ef6  ldarg.0
0x124ef7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124efc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x124f01  ldarg.0
0x124f02  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::okButton
0x124f07  ldc.i4.0
0x124f08  ldc.i4.0
0x124f09  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x124f0e  ldarg.0
0x124f0f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124f14  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x124f19  ldarg.0
0x124f1a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnCancel
0x124f1f  ldc.i4.1
0x124f20  ldc.i4.0
0x124f21  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x124f26  ldarg.0
0x124f27  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124f2c  ldc.i4.3
0x124f2d  ldc.i4.3
0x124f2e  ldc.i4.0
0x124f2f  ldc.i4.0
0x124f30  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x124f35  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x124f3a  ldarg.0
0x124f3b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124f40  ldstr    aOkcancelpanel// "okCancelPanel"
0x124f45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x124f4a  ldarg.0
0x124f4b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::okCancelPanel
0x124f50  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x124f55  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x124f5a  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x124f5f  pop
0x124f60  ldloc.0
0x124f61  ldarg.0
0x124f62  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::okButton
0x124f67  ldstr    aOkbutton_0// "okButton"
0x124f6c  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x124f71  ldarg.0
0x124f72  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::okButton
0x124f77  ldc.i4.1
0x124f78  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x124f7d  ldarg.0
0x124f7e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::okButton
0x124f83  ldc.i4.0
0x124f84  ldc.i4.0
0x124f85  ldc.i4.3
0x124f86  ldc.i4.0
0x124f87  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x124f8c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x124f91  ldarg.0
0x124f92  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::okButton
0x124f97  ldstr    aOkbutton_0// "okButton"
0x124f9c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x124fa1  ldloc.0
0x124fa2  ldarg.0
0x124fa3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnCancel
0x124fa8  ldstr    aBtncancel// "btnCancel"
0x124fad  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x124fb2  ldarg.0
0x124fb3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnCancel
0x124fb8  ldc.i4.2
0x124fb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x124fbe  ldarg.0
0x124fbf  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnCancel
0x124fc4  ldc.i4.3
0x124fc5  ldc.i4.0
0x124fc6  ldc.i4.0
0x124fc7  ldc.i4.0
0x124fc8  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x124fcd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x124fd2  ldarg.0
0x124fd3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnCancel
0x124fd8  ldstr    aBtncancel// "btnCancel"
0x124fdd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x124fe2  ldloc.0
0x124fe3  ldarg.0
0x124fe4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x124fe9  ldstr    aNodecontrolpan// "nodeControlPanel"
0x124fee  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x124ff3  ldarg.0
0x124ff4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x124ff9  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x124ffe  ldc.i4.2
0x124fff  ldc.r4   50.0
0x125004  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x125009  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x12500e  pop
0x12500f  ldarg.0
0x125010  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x125015  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x12501a  ldc.i4.2
0x12501b  ldc.r4   50.0
0x125020  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x125025  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x12502a  pop
0x12502b  ldarg.0
0x12502c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x125031  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x125036  ldarg.0
0x125037  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddRoot
0x12503c  ldc.i4.0
0x12503d  ldc.i4.0
0x12503e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x125043  ldarg.0
0x125044  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x125049  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x12504e  ldarg.0
0x12504f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddChild
0x125054  ldc.i4.1
0x125055  ldc.i4.0
0x125056  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x12505b  ldarg.0
0x12505c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x125061  ldc.i4.0
0x125062  ldc.i4.3
0x125063  ldc.i4.3
0x125064  ldc.i4.3
0x125065  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x12506a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x12506f  ldarg.0
0x125070  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x125075  ldstr    aNodecontrolpan// "nodeControlPanel"
0x12507a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x12507f  ldarg.0
0x125080  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel TreeNodeCollectionForm::nodeControlPanel
0x125085  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x12508a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x12508f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x125094  pop
0x125095  ldloc.0
0x125096  ldarg.0
0x125097  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddRoot
0x12509c  ldstr    aBtnaddroot// "btnAddRoot"
0x1250a1  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1250a6  ldarg.0
0x1250a7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddRoot
0x1250ac  ldc.i4.0
0x1250ad  ldc.i4.0
0x1250ae  ldc.i4.3
0x1250af  ldc.i4.0
0x1250b0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x1250b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1250ba  ldarg.0
0x1250bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddRoot
0x1250c0  ldstr    aBtnaddroot// "btnAddRoot"
0x1250c5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1250ca  ldloc.0
0x1250cb  ldarg.0
0x1250cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddChild
0x1250d1  ldstr    aBtnaddchild// "btnAddChild"
0x1250d6  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1250db  ldarg.0
0x1250dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddChild
0x1250e1  ldc.i4.3
0x1250e2  ldc.i4.0
0x1250e3  ldc.i4.0
0x1250e4  ldc.i4.0
0x1250e5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x1250ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1250ef  ldarg.0
0x1250f0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnAddChild
0x1250f5  ldstr    aBtnaddchild// "btnAddChild"
0x1250fa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1250ff  ldloc.0
0x125100  ldarg.0
0x125101  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnDelete
0x125106  ldstr    aBtndelete// "btnDelete"
0x12510b  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x125110  ldarg.0
0x125111  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnDelete
0x125116  ldc.i4.0
0x125117  ldc.i4.3
0x125118  ldc.i4.0
0x125119  ldc.i4.0
0x12511a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x12511f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x125124  ldarg.0
0x125125  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::btnDelete
0x12512a  ldstr    aBtndelete// "btnDelete"
0x12512f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x125134  ldloc.0
0x125135  ldarg.0
0x125136  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::moveDownButton
0x12513b  ldstr    aMovedownbutton_0// "moveDownButton"
0x125140  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x125145  ldarg.0
0x125146  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::moveDownButton
0x12514b  ldc.i4.0
0x12514c  ldc.i4.1
0x12514d  ldc.i4.0
0x12514e  ldc.i4.3
0x12514f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x125154  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x125159  ldarg.0
0x12515a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::moveDownButton
0x12515f  ldstr    aMovedownbutton_0// "moveDownButton"
0x125164  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x125169  ldloc.0
0x12516a  ldarg.0
0x12516b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::moveUpButton
0x125170  ldstr    aMoveupbutton_0// "moveUpButton"
0x125175  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x12517a  ldarg.0
0x12517b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::moveUpButton
0x125180  ldc.i4.0
0x125181  ldc.i4.0
0x125182  ldc.i4.0
0x125183  ldc.i4.1
0x125184  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x125189  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x12518e  ldarg.0
0x12518f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button TreeNodeCollectionForm::moveUpButton
  ... truncated ...
```
