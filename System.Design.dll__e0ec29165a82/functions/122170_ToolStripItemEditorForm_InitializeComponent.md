# ToolStripItemEditorForm::InitializeComponent

- ea: `0x122170`
- end: `0x122aec`
- name: `ToolStripItemEditorForm::InitializeComponent`
- size: `2428`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x121eb0`

## callees

- `0xe3d40`
- `0x105ff0`
- `0x1060b0`
- `0x12b170`

## string_xrefs

- `0x122750`: `selectedItemProps`
- `0x122774`: `selectedItemProps`
- `0x122837`: `btnMoveUp`
- `0x12285c`: `btnMoveUp`
- `0x12286d`: `btnMoveDown`
- `0x122892`: `btnMoveDown`
- `0x1228a3`: `btnRemove`
- `0x1228c8`: `btnRemove`

## pseudocode

```c

```

## disassembly

```asm
0x122170  ldtoken  ToolStripItemEditorForm
0x122175  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12217a  newobj   instance void [System]System.ComponentModel.ComponentResourceManager::.ctor(class [mscorlib]System.Type)
0x12217f  stloc.0
0x122180  ldarg.0
0x122181  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x122186  stfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnCancel
0x12218b  ldarg.0
0x12218c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x122191  stfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnOK
0x122196  ldarg.0
0x122197  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x12219c  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1221a1  ldarg.0
0x1221a2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1221a7  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x1221ac  ldarg.0
0x1221ad  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x1221b2  stfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnAddNew
0x1221b7  ldarg.0
0x1221b8  newobj   instance void ImageComboBox::.ctor()
0x1221bd  stfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ToolStripItemEditorForm::newItemTypes
0x1221c2  ldarg.0
0x1221c3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::.ctor()
0x1221c8  stfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::okCancelTableLayoutPanel
0x1221cd  ldarg.0
0x1221ce  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1221d3  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ToolStripItemEditorForm::lblItems
0x1221d8  ldarg.0
0x1221d9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1221de  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ToolStripItemEditorForm::selectedItemName
0x1221e3  ldarg.0
0x1221e4  ldarg.0
0x1221e5  call     instance class [System]System.ComponentModel.ITypeDescriptorContext CollectionForm::get_Context()
0x1221ea  newobj   instance void System.Windows.Forms.Design.VsPropertyGrid::.ctor(class [mscorlib]System.IServiceProvider serviceProvider)
0x1221ef  stfld    class System.Windows.Forms.Design.VsPropertyGrid ToolStripItemEditorForm::selectedItemProps
0x1221f4  ldarg.0
0x1221f5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x1221fa  stfld    class [System.Windows.Forms]System.Windows.Forms.Label ToolStripItemEditorForm::lblMembers
0x1221ff  ldarg.0
0x122200  newobj   instance void FilterListBox::.ctor()
0x122205  stfld    class FilterListBox ToolStripItemEditorForm::listBoxItems
0x12220a  ldarg.0
0x12220b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x122210  stfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnMoveUp
0x122215  ldarg.0
0x122216  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x12221b  stfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnMoveDown
0x122220  ldarg.0
0x122221  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x122226  stfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnRemove
0x12222b  ldarg.0
0x12222c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x122231  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x122236  ldarg.0
0x122237  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x12223c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x122241  ldarg.0
0x122242  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::okCancelTableLayoutPanel
0x122247  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x12224c  ldarg.0
0x12224d  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x122252  ldloc.0
0x122253  ldarg.0
0x122254  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnCancel
0x122259  ldstr    aBtncancel// "btnCancel"
0x12225e  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x122263  ldarg.0
0x122264  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnCancel
0x122269  ldc.i4.2
0x12226a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Button::set_DialogResult(valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult)
0x12226f  ldarg.0
0x122270  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnCancel
0x122275  ldc.i4.3
0x122276  ldc.i4.0
0x122277  ldc.i4.0
0x122278  ldc.i4.0
0x122279  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x12227e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x122283  ldarg.0
0x122284  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnCancel
0x122289  ldstr    aBtncancel// "btnCancel"
0x12228e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x122293  ldloc.0
0x122294  ldarg.0
0x122295  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnOK
0x12229a  ldstr    aBtnok// "btnOK"
0x12229f  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1222a4  ldarg.0
0x1222a5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnOK
0x1222aa  ldc.i4.0
0x1222ab  ldc.i4.0
0x1222ac  ldc.i4.3
0x1222ad  ldc.i4.0
0x1222ae  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x1222b3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x1222b8  ldarg.0
0x1222b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnOK
0x1222be  ldstr    aBtnok// "btnOK"
0x1222c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x1222c8  ldloc.0
0x1222c9  ldarg.0
0x1222ca  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1222cf  ldstr    aTablelayoutpan_30// "tableLayoutPanel"
0x1222d4  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1222d9  ldarg.0
0x1222da  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1222df  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x1222e4  ldc.i4.1
0x1222e5  ldc.r4   274.0
0x1222ea  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x1222ef  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x1222f4  pop
0x1222f5  ldarg.0
0x1222f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1222fb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x122300  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor()
0x122305  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x12230a  pop
0x12230b  ldarg.0
0x12230c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x122311  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x122316  ldc.i4.2
0x122317  ldc.r4   100.0
0x12231c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x122321  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x122326  pop
0x122327  ldarg.0
0x122328  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x12232d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x122332  ldarg.0
0x122333  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x122338  ldc.i4.0
0x122339  ldc.i4.1
0x12233a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x12233f  ldarg.0
0x122340  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x122345  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x12234a  ldarg.0
0x12234b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::okCancelTableLayoutPanel
0x122350  ldc.i4.0
0x122351  ldc.i4.6
0x122352  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x122357  ldarg.0
0x122358  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x12235d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x122362  ldarg.0
0x122363  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ToolStripItemEditorForm::lblItems
0x122368  ldc.i4.0
0x122369  ldc.i4.0
0x12236a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x12236f  ldarg.0
0x122370  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x122375  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x12237a  ldarg.0
0x12237b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ToolStripItemEditorForm::selectedItemName
0x122380  ldc.i4.2
0x122381  ldc.i4.0
0x122382  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x122387  ldarg.0
0x122388  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x12238d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x122392  ldarg.0
0x122393  ldfld    class System.Windows.Forms.Design.VsPropertyGrid ToolStripItemEditorForm::selectedItemProps
0x122398  ldc.i4.2
0x122399  ldc.i4.1
0x12239a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x12239f  ldarg.0
0x1223a0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1223a5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1223aa  ldarg.0
0x1223ab  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label ToolStripItemEditorForm::lblMembers
0x1223b0  ldc.i4.0
0x1223b1  ldc.i4.2
0x1223b2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1223b7  ldarg.0
0x1223b8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1223bd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1223c2  ldarg.0
0x1223c3  ldfld    class FilterListBox ToolStripItemEditorForm::listBoxItems
0x1223c8  ldc.i4.0
0x1223c9  ldc.i4.3
0x1223ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1223cf  ldarg.0
0x1223d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1223d5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1223da  ldarg.0
0x1223db  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnMoveUp
0x1223e0  ldc.i4.1
0x1223e1  ldc.i4.3
0x1223e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1223e7  ldarg.0
0x1223e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1223ed  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x1223f2  ldarg.0
0x1223f3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnMoveDown
0x1223f8  ldc.i4.1
0x1223f9  ldc.i4.4
0x1223fa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x1223ff  ldarg.0
0x122400  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x122405  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x12240a  ldarg.0
0x12240b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnRemove
0x122410  ldc.i4.1
0x122411  ldc.i4.5
0x122412  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x122417  ldarg.0
0x122418  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x12241d  ldstr    aTablelayoutpan_30// "tableLayoutPanel"
0x122422  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x122427  ldarg.0
0x122428  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x12242d  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x122432  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x122437  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x12243c  pop
0x12243d  ldarg.0
0x12243e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x122443  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x122448  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x12244d  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x122452  pop
0x122453  ldarg.0
0x122454  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x122459  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x12245e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x122463  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x122468  pop
0x122469  ldarg.0
0x12246a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x12246f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x122474  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x122479  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x12247e  pop
0x12247f  ldarg.0
0x122480  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x122485  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x12248a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x12248f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x122494  pop
0x122495  ldarg.0
0x122496  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x12249b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x1224a0  ldc.i4.2
0x1224a1  ldc.r4   100.0
0x1224a6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x1224ab  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x1224b0  pop
0x1224b1  ldarg.0
0x1224b2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::tableLayoutPanel
0x1224b7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0x1224bc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.RowStyle::.ctor()
0x1224c1  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.RowStyle)
0x1224c6  pop
0x1224c7  ldloc.0
0x1224c8  ldarg.0
0x1224c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x1224ce  ldstr    aAddtablelayout// "addTableLayoutPanel"
0x1224d3  callvirt instance void [System]System.ComponentModel.ComponentResourceManager::ApplyResources(object, string)
0x1224d8  ldarg.0
0x1224d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x1224de  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x1224e3  ldc.i4.2
0x1224e4  ldc.r4   100.0
0x1224e9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor(valuetype [System.Windows.Forms]System.Windows.Forms.SizeType, float32)
0x1224ee  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x1224f3  pop
0x1224f4  ldarg.0
0x1224f5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x1224fa  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0x1224ff  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ColumnStyle::.ctor()
0x122504  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ColumnStyle)
0x122509  pop
0x12250a  ldarg.0
0x12250b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x122510  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x122515  ldarg.0
0x122516  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button ToolStripItemEditorForm::btnAddNew
0x12251b  ldc.i4.1
0x12251c  ldc.i4.0
0x12251d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x122522  ldarg.0
0x122523  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x122528  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_Controls()
0x12252d  ldarg.0
0x12252e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ComboBox ToolStripItemEditorForm::newItemTypes
0x122533  ldc.i4.0
0x122534  ldc.i4.0
0x122535  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TableLayoutControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control, int32, int32)
0x12253a  ldarg.0
0x12253b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
0x122540  ldc.i4.0
0x122541  ldc.i4.3
0x122542  ldc.i4.3
0x122543  ldc.i4.3
0x122544  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32, int32, int32, int32)
0x122549  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0x12254e  ldarg.0
0x12254f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel ToolStripItemEditorForm::addTableLayoutPanel
  ... truncated ...
```
