# System.Windows.Forms.Design.TableLayoutPanelDesigner::OnRowColMenuOpening

- ea: `0xccc00`
- end: `0xcce2b`
- name: `System.Windows.Forms.Design.TableLayoutPanelDesigner::OnRowColMenuOpening`
- size: `555`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x58560`
- `0x58ca0`
- `0xcadf0`
- `0xccc00`

## string_xrefs

- `0xccc80`: `delete`
- `0xcce1a`: `delete`

## pseudocode

```c

```

## disassembly

```asm
0xccc00  ldarg.2
0xccc01  ldc.i4.0
0xccc02  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0xccc07  ldarg.1
0xccc08  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownMenu
0xccc0d  stloc.0
0xccc0e  ldloc.0
0xccc0f  brfalse  loc_CCE2A
0xccc14  ldc.i4.0
0xccc15  stloc.1
0xccc16  ldarg.0
0xccc17  ldtoken  [System]System.ComponentModel.Design.ISelectionService
0xccc1c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xccc21  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xccc26  isinst   [System]System.ComponentModel.Design.ISelectionService
0xccc2b  stloc.2
0xccc2c  ldloc.2
0xccc2d  brfalse.s loc_CCC36
0xccc2f  ldloc.2
0xccc30  callvirt instance int32 [System]System.ComponentModel.Design.ISelectionService::get_SelectionCount()
0xccc35  stloc.1
0xccc36  ldloc.1
0xccc37  ldc.i4.1
0xccc38  bne.un.s loc_CCC4C
0xccc3a  ldarg.0
0xccc3b  callvirt instance class [System]System.ComponentModel.InheritanceAttribute System.ComponentModel.Design.ComponentDesigner::get_InheritanceAttribute()
0xccc40  ldsfld   class [System]System.ComponentModel.InheritanceAttribute [System]System.ComponentModel.InheritanceAttribute::InheritedReadOnly
0xccc45  ceq
0xccc47  ldc.i4.0
0xccc48  ceq
0xccc4a  br.s     loc_CCC4D
0xccc4c  ldc.i4.0
0xccc4d  stloc.3
0xccc4e  ldloc.0
0xccc4f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccc54  ldstr    aAdd_1// "add"
0xccc59  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccc5e  ldloc.3
0xccc5f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xccc64  ldloc.0
0xccc65  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccc6a  ldstr    aInsert_1// "insert"
0xccc6f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccc74  ldloc.3
0xccc75  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xccc7a  ldloc.0
0xccc7b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccc80  ldstr    aDelete_1// "delete"
0xccc85  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccc8a  ldloc.3
0xccc8b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xccc90  ldloc.0
0xccc91  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccc96  ldstr    aSizemode_0// "sizemode"
0xccc9b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccca0  ldloc.3
0xccca1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xccca6  ldloc.0
0xccca7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xcccac  ldstr    aAbsolute// "absolute"
0xcccb1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xcccb6  ldloc.3
0xcccb7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xcccbc  ldloc.0
0xcccbd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xcccc2  ldstr    aPercent// "percent"
0xcccc7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccccc  ldloc.3
0xccccd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xcccd2  ldloc.0
0xcccd3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xcccd8  ldstr    aAutosize_0// "autosize"
0xcccdd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccce2  ldloc.3
0xccce3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xccce8  ldloc.1
0xccce9  ldc.i4.1
0xcccea  bne.un   loc_CCE2A
0xcccef  ldloc.0
0xcccf0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xcccf5  ldstr    aAbsolute// "absolute"
0xcccfa  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xcccff  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem
0xccd04  ldc.i4.0
0xccd05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::set_Checked(bool)
0xccd0a  ldloc.0
0xccd0b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccd10  ldstr    aPercent// "percent"
0xccd15  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccd1a  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem
0xccd1f  ldc.i4.0
0xccd20  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::set_Checked(bool)
0xccd25  ldloc.0
0xccd26  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccd2b  ldstr    aAutosize_0// "autosize"
0xccd30  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccd35  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem
0xccd3a  ldc.i4.0
0xccd3b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::set_Checked(bool)
0xccd40  ldloc.0
0xccd41  callvirt instance object [System.Windows.Forms]System.Windows.Forms.Control::get_Tag()
0xccd46  unbox.any [mscorlib]System.Boolean
0xccd4b  stloc.s  4
0xccd4d  ldloc.s  4
0xccd4f  brtrue.s loc_CCD6E
0xccd51  ldarg.0
0xccd52  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xccd57  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnStyles()
0xccd5c  ldarg.0
0xccd5d  ldfld    int32 System.Windows.Forms.Design.TableLayoutPanelDesigner::curCol
0xccd62  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ColumnStyle [System.Windows.Forms]System.Windows.Forms.TableLayoutColumnStyleCollection::get_Item(int32)
0xccd67  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.SizeType [System.Windows.Forms]System.Windows.Forms.TableLayoutStyle::get_SizeType()
0xccd6c  br.s     loc_CCD89
0xccd6e  ldarg.0
0xccd6f  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xccd74  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowStyles()
0xccd79  ldarg.0
0xccd7a  ldfld    int32 System.Windows.Forms.Design.TableLayoutPanelDesigner::curRow
0xccd7f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.RowStyle [System.Windows.Forms]System.Windows.Forms.TableLayoutRowStyleCollection::get_Item(int32)
0xccd84  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.SizeType [System.Windows.Forms]System.Windows.Forms.TableLayoutStyle::get_SizeType()
0xccd89  stloc.s  5
0xccd8b  ldloc.s  5
0xccd8d  switch   loc_CCDDA, loc_CCDA0, loc_CCDBD
0xccd9e  br.s     loc_CCDF5
0xccda0  ldloc.0
0xccda1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccda6  ldstr    aAbsolute// "absolute"
0xccdab  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccdb0  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem
0xccdb5  ldc.i4.1
0xccdb6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::set_Checked(bool)
0xccdbb  br.s     loc_CCDF5
0xccdbd  ldloc.0
0xccdbe  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccdc3  ldstr    aPercent// "percent"
0xccdc8  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccdcd  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem
0xccdd2  ldc.i4.1
0xccdd3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::set_Checked(bool)
0xccdd8  br.s     loc_CCDF5
0xccdda  ldloc.0
0xccddb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xccde0  ldstr    aAutosize_0// "autosize"
0xccde5  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xccdea  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem
0xccdef  ldc.i4.1
0xccdf0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::set_Checked(bool)
0xccdf5  ldloc.s  4
0xccdf7  brtrue.s loc_CCE06
0xccdf9  ldarg.0
0xccdfa  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xccdff  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_ColumnCount()
0xcce04  br.s     loc_CCE11
0xcce06  ldarg.0
0xcce07  call     instance class [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel System.Windows.Forms.Design.TableLayoutPanelDesigner::get_Table()
0xcce0c  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.TableLayoutPanel::get_RowCount()
0xcce11  ldc.i4.2
0xcce12  bge.s    loc_CCE2A
0xcce14  ldloc.0
0xcce15  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xcce1a  ldstr    aDelete_1// "delete"
0xcce1f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(string)
0xcce24  ldc.i4.0
0xcce25  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Enabled(bool)
0xcce2a  ret
```
