# System.Windows.Forms.Design.TableLayoutPanelDesigner::BuildMenu

- ea: `0xcb060`
- end: `0xcb30a`
- name: `System.Windows.Forms.Design.TableLayoutPanelDesigner::BuildMenu`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0xcab50`

## callees

- `0x58ca0`
- `0x8ef40`
- `0xcb060`

## string_xrefs

- `0xcb123`: `delete`
- `0xcb107`: `TableLayoutPanelDesignerDeleteMenu`

## pseudocode

```c

```

## disassembly

```asm
0xcb060  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0xcb065  stloc.0
0xcb066  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0xcb06b  stloc.1
0xcb06c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0xcb071  stloc.2
0xcb072  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripSeparator::.ctor()
0xcb077  stloc.3
0xcb078  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripLabel::.ctor()
0xcb07d  stloc.s  4
0xcb07f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0xcb084  stloc.s  5
0xcb086  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0xcb08b  stloc.s  6
0xcb08d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripMenuItem::.ctor()
0xcb092  stloc.s  7
0xcb094  ldloc.0
0xcb095  ldstr    aTablelayoutpan_13// "TableLayoutPanelDesignerAddMenu"
0xcb09a  call     string System.Design.SR::GetString(string name)
0xcb09f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcb0a4  ldloc.0
0xcb0a5  ldarg.1
0xcb0a6  box      [mscorlib]System.Boolean
0xcb0ab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Tag(object)
0xcb0b0  ldloc.0
0xcb0b1  ldstr    aAdd_1// "add"
0xcb0b6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0xcb0bb  ldloc.0
0xcb0bc  ldarg.0
0xcb0bd  ldftn    instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::OnAddClick(object sender, class [mscorlib]System.EventArgs e)
0xcb0c3  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xcb0c8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0xcb0cd  ldloc.1
0xcb0ce  ldstr    aTablelayoutpan_14// "TableLayoutPanelDesignerInsertMenu"
0xcb0d3  call     string System.Design.SR::GetString(string name)
0xcb0d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcb0dd  ldloc.1
0xcb0de  ldarg.1
0xcb0df  box      [mscorlib]System.Boolean
0xcb0e4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Tag(object)
0xcb0e9  ldloc.1
0xcb0ea  ldstr    aInsert_1// "insert"
0xcb0ef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0xcb0f4  ldloc.1
0xcb0f5  ldarg.0
0xcb0f6  ldftn    instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::OnInsertClick(object sender, class [mscorlib]System.EventArgs e)
0xcb0fc  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xcb101  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0xcb106  ldloc.2
0xcb107  ldstr    aTablelayoutpan_15// "TableLayoutPanelDesignerDeleteMenu"
0xcb10c  call     string System.Design.SR::GetString(string name)
0xcb111  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcb116  ldloc.2
0xcb117  ldarg.1
0xcb118  box      [mscorlib]System.Boolean
0xcb11d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Tag(object)
0xcb122  ldloc.2
0xcb123  ldstr    aDelete_1// "delete"
0xcb128  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0xcb12d  ldloc.2
0xcb12e  ldarg.0
0xcb12f  ldftn    instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::OnDeleteClick(object sender, class [mscorlib]System.EventArgs e)
0xcb135  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xcb13a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0xcb13f  ldloc.s  4
0xcb141  ldstr    aTablelayoutpan_16// "TableLayoutPanelDesignerLabelMenu"
0xcb146  call     string System.Design.SR::GetString(string name)
0xcb14b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcb150  ldstr    aTablelayoutpan_17// "TableLayoutPanelDesignerDontBoldLabel"
0xcb155  call     string System.Design.SR::GetString(string name)
0xcb15a  ldstr    a0_1// "0"
0xcb15f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcb164  brfalse.s loc_CB17A
0xcb166  ldloc.s  4
0xcb168  ldloc.s  4
0xcb16a  callvirt instance class [System.Drawing]System.Drawing.Font [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Font()
0xcb16f  ldc.i4.1
0xcb170  newobj   instance void [System.Drawing]System.Drawing.Font::.ctor(class [System.Drawing]System.Drawing.Font, valuetype [System.Drawing]System.Drawing.FontStyle)
0xcb175  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Font(class [System.Drawing]System.Drawing.Font)
0xcb17a  ldloc.s  4
0xcb17c  ldstr    aSizemode_0// "sizemode"
0xcb181  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0xcb186  ldloc.s  5
0xcb188  ldstr    aTablelayoutpan_18// "TableLayoutPanelDesignerAbsoluteMenu"
0xcb18d  call     string System.Design.SR::GetString(string name)
0xcb192  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcb197  ldloc.s  5
0xcb199  ldarg.1
0xcb19a  box      [mscorlib]System.Boolean
0xcb19f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Tag(object)
0xcb1a4  ldloc.s  5
0xcb1a6  ldstr    aAbsolute// "absolute"
0xcb1ab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0xcb1b0  ldloc.s  5
0xcb1b2  ldarg.0
0xcb1b3  ldftn    instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::OnAbsoluteClick(object sender, class [mscorlib]System.EventArgs e)
0xcb1b9  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xcb1be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0xcb1c3  ldloc.s  6
0xcb1c5  ldstr    aTablelayoutpan_19// "TableLayoutPanelDesignerPercentageMenu"
0xcb1ca  call     string System.Design.SR::GetString(string name)
0xcb1cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcb1d4  ldloc.s  6
0xcb1d6  ldarg.1
0xcb1d7  box      [mscorlib]System.Boolean
0xcb1dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Tag(object)
0xcb1e1  ldloc.s  6
0xcb1e3  ldstr    aPercent// "percent"
0xcb1e8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0xcb1ed  ldloc.s  6
0xcb1ef  ldarg.0
0xcb1f0  ldftn    instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::OnPercentClick(object sender, class [mscorlib]System.EventArgs e)
0xcb1f6  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xcb1fb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0xcb200  ldloc.s  7
0xcb202  ldstr    aTablelayoutpan_20// "TableLayoutPanelDesignerAutoSizeMenu"
0xcb207  call     string System.Design.SR::GetString(string name)
0xcb20c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Text(string)
0xcb211  ldloc.s  7
0xcb213  ldarg.1
0xcb214  box      [mscorlib]System.Boolean
0xcb219  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Tag(object)
0xcb21e  ldloc.s  7
0xcb220  ldstr    aAutosize_0// "autosize"
0xcb225  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Name(string)
0xcb22a  ldloc.s  7
0xcb22c  ldarg.0
0xcb22d  ldftn    instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::OnAutoSizeClick(object sender, class [mscorlib]System.EventArgs e)
0xcb233  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xcb238  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_Click(class [mscorlib]System.EventHandler)
0xcb23d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownMenu::.ctor()
0xcb242  stloc.s  8
0xcb244  ldloc.s  8
0xcb246  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xcb24b  ldc.i4.8
0xcb24c  newarr   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0xcb251  dup
0xcb252  ldc.i4.0
0xcb253  ldloc.0
0xcb254  stelem.ref
0xcb255  dup
0xcb256  ldc.i4.1
0xcb257  ldloc.1
0xcb258  stelem.ref
0xcb259  dup
0xcb25a  ldc.i4.2
0xcb25b  ldloc.2
0xcb25c  stelem.ref
0xcb25d  dup
0xcb25e  ldc.i4.3
0xcb25f  ldloc.3
0xcb260  stelem.ref
0xcb261  dup
0xcb262  ldc.i4.4
0xcb263  ldloc.s  4
0xcb265  stelem.ref
0xcb266  dup
0xcb267  ldc.i4.5
0xcb268  ldloc.s  5
0xcb26a  stelem.ref
0xcb26b  dup
0xcb26c  ldc.i4.6
0xcb26d  ldloc.s  6
0xcb26f  stelem.ref
0xcb270  dup
0xcb271  ldc.i4.7
0xcb272  ldloc.s  7
0xcb274  stelem.ref
0xcb275  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem[])
0xcb27a  ldloc.s  8
0xcb27c  ldarg.1
0xcb27d  box      [mscorlib]System.Boolean
0xcb282  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Tag(object)
0xcb287  ldloc.s  8
0xcb289  ldarg.0
0xcb28a  ldftn    instance void System.Windows.Forms.Design.TableLayoutPanelDesigner::OnRowColMenuOpening(object sender, class [System]System.ComponentModel.CancelEventArgs e)
0xcb290  newobj   instance void [System]System.ComponentModel.CancelEventHandler::.ctor(object, native int)
0xcb295  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown::add_Opening(class [System]System.ComponentModel.CancelEventHandler)
0xcb29a  ldarg.0
0xcb29b  ldtoken  [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xcb2a0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xcb2a5  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xcb2aa  isinst   [System.Windows.Forms]System.Windows.Forms.Design.IUIService
0xcb2af  stloc.s  9
0xcb2b1  ldloc.s  9
0xcb2b3  brfalse.s loc_CB307
0xcb2b5  ldloc.s  8
0xcb2b7  ldloc.s  9
0xcb2b9  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0xcb2be  ldstr    aVsrenderer// "VsRenderer"
0xcb2c3  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xcb2c8  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripProfessionalRenderer
0xcb2cd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_Renderer(class [System.Windows.Forms]System.Windows.Forms.ToolStripRenderer)
0xcb2d2  ldloc.s  9
0xcb2d4  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0xcb2d9  ldstr    aVscolorpanelte// "VsColorPanelText"
0xcb2de  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xcb2e3  isinst   [System.Drawing]System.Drawing.Color
0xcb2e8  brfalse.s loc_CB307
0xcb2ea  ldloc.s  8
0xcb2ec  ldloc.s  9
0xcb2ee  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Windows.Forms]System.Windows.Forms.Design.IUIService::get_Styles()
0xcb2f3  ldstr    aVscolorpanelte// "VsColorPanelText"
0xcb2f8  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0xcb2fd  unbox.any [System.Drawing]System.Drawing.Color
0xcb302  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStrip::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0xcb307  ldloc.s  8
0xcb309  ret
```
