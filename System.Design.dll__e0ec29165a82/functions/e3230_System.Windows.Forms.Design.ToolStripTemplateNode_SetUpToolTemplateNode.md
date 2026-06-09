# System.Windows.Forms.Design.ToolStripTemplateNode::SetUpToolTemplateNode

- ea: `0xe3230`
- end: `0xe3464`
- name: `System.Windows.Forms.Design.ToolStripTemplateNode::SetUpToolTemplateNode`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0xe3470`

## callees

- `0x8ef40`
- `0x8efb0`
- `0x8f6c0`
- `0x8f780`
- `0xd5970`
- `0xe3230`
- `0xef2e0`

## string_xrefs

- `0xe32b9`: `ToolStripDesignerTemplateNodeSplitButtonStatusStripToolTip`
- `0xe32d0`: `ToolStripDesignerTemplateNodeSplitButtonToolTip`
- `0xe33f1`: `ToolStripTemplateNode.bmp`

## pseudocode

```c

```

## disassembly

```asm
0xe3230  ldarg.0
0xe3231  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton::.ctor()
0xe3236  stfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe323b  ldarg.0
0xe323c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe3241  ldc.i4.0
0xe3242  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_AutoSize(bool)
0xe3247  ldarg.0
0xe3248  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe324d  ldc.i4.1
0xe324e  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Padding::.ctor(int32)
0xe3253  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Margin(valuetype [System.Windows.Forms]System.Windows.Forms.Padding)
0xe3258  ldarg.0
0xe3259  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe325e  ldarg.0
0xe325f  ldfld    class TransparentToolStrip System.Windows.Forms.Design.ToolStripTemplateNode::_miniToolStrip
0xe3264  callvirt instance valuetype [System.Drawing]System.Drawing.Rectangle [System.Windows.Forms]System.Windows.Forms.Control::get_DisplayRectangle()
0xe3269  stloc.0
0xe326a  ldloca.s 0
0xe326c  call     instance valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Rectangle::get_Size()
0xe3271  ldarg.0
0xe3272  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe3277  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.Padding [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Margin()
0xe327c  stloc.1
0xe327d  ldloca.s 1
0xe327f  call     instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Padding::get_Size()
0xe3284  call     valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::op_Subtraction(valuetype [System.Drawing]System.Drawing.Size, valuetype [System.Drawing]System.Drawing.Size)
0xe3289  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xe328e  ldarg.0
0xe328f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe3294  ldsfld   int32 System.Windows.Forms.Design.ToolStripTemplateNode::MINITOOLSTRIP_DROPDOWN_BUTTON_WIDTH
0xe3299  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton::set_DropDownButtonWidth(int32)
0xe329e  ldarg.0
0xe329f  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe32a4  ldc.i4.2
0xe32a5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_DisplayStyle(valuetype [System.Windows.Forms]System.Windows.Forms.ToolStripItemDisplayStyle)
0xe32aa  ldarg.s  4
0xe32ac  isinst   [System.Windows.Forms]System.Windows.Forms.StatusStrip
0xe32b1  brfalse.s loc_E32CA
0xe32b3  ldarg.0
0xe32b4  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe32b9  ldstr    aToolstripdesig_7// "ToolStripDesignerTemplateNodeSplitButto"...
0xe32be  call     string System.Design.SR::GetString(string name)
0xe32c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_ToolTipText(string)
0xe32c8  br.s     loc_E32DF
0xe32ca  ldarg.0
0xe32cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe32d0  ldstr    aToolstripdesig_8// "ToolStripDesignerTemplateNodeSplitButto"...
0xe32d5  call     string System.Design.SR::GetString(string name)
0xe32da  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_ToolTipText(string)
0xe32df  ldarg.0
0xe32e0  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe32e5  ldarg.0
0xe32e6  ldftn    instance void System.Windows.Forms.Design.ToolStripTemplateNode::OnMouseDown(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0xe32ec  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0xe32f1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_MouseDown(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0xe32f6  ldarg.0
0xe32f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe32fc  ldarg.0
0xe32fd  ldftn    instance void System.Windows.Forms.Design.ToolStripTemplateNode::OnMouseMove(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0xe3303  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0xe3308  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_MouseMove(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0xe330d  ldarg.0
0xe330e  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe3313  ldarg.0
0xe3314  ldftn    instance void System.Windows.Forms.Design.ToolStripTemplateNode::OnMouseUp(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0xe331a  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0xe331f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::add_MouseUp(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0xe3324  ldarg.0
0xe3325  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe332a  ldarg.0
0xe332b  ldftn    instance void System.Windows.Forms.Design.ToolStripTemplateNode::OnAddItemButtonDropDownOpened(object sender, class [mscorlib]System.EventArgs e)
0xe3331  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xe3336  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem::add_DropDownOpened(class [mscorlib]System.EventHandler)
0xe333b  ldarg.0
0xe333c  ldarg.s  4
0xe333e  ldnull
0xe333f  ldarg.0
0xe3340  ldftn    instance void System.Windows.Forms.Design.ToolStripTemplateNode::AddNewItemClick(object sender, class [mscorlib]System.EventArgs e)
0xe3346  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xe334b  ldc.i4.0
0xe334c  ldarg.s  4
0xe334e  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xe3353  ldc.i4.0
0xe3354  call     class System.Windows.Forms.Design.NewItemsContextMenuStrip System.Windows.Forms.Design.ToolStripDesignerUtils::GetNewItemDropDown(class [System]System.ComponentModel.IComponent component, class [System.Windows.Forms]System.Windows.Forms.ToolStripItem currentItem, class [mscorlib]System.EventHandler onClick, bool convertTo, class [mscorlib]System.IServiceProvider serviceProvider, bool populateCustom)
0xe3359  stfld    class System.Windows.Forms.Design.NewItemsContextMenuStrip System.Windows.Forms.Design.ToolStripTemplateNode::contextMenu
0xe335e  ldarg.0
0xe335f  ldfld    class System.Windows.Forms.Design.NewItemsContextMenuStrip System.Windows.Forms.Design.ToolStripTemplateNode::contextMenu
0xe3364  ldstr    aItemselectionm// "ItemSelectionMenu"
0xe3369  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xe336e  ldarg.0
0xe336f  ldfld    class System.Windows.Forms.Design.NewItemsContextMenuStrip System.Windows.Forms.Design.ToolStripTemplateNode::contextMenu
0xe3374  ldarg.0
0xe3375  ldftn    instance void System.Windows.Forms.Design.ToolStripTemplateNode::OnContextMenuClosed(object sender, class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownClosedEventArgs e)
0xe337b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownClosedEventHandler::.ctor(object, native int)
0xe3380  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown::add_Closed(class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownClosedEventHandler)
0xe3385  ldarg.0
0xe3386  ldfld    class System.Windows.Forms.Design.NewItemsContextMenuStrip System.Windows.Forms.Design.ToolStripTemplateNode::contextMenu
0xe338b  ldarg.0
0xe338c  ldftn    instance void System.Windows.Forms.Design.ToolStripTemplateNode::OnContextMenuOpened(object sender, class [mscorlib]System.EventArgs e)
0xe3392  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xe3397  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown::add_Opened(class [mscorlib]System.EventHandler)
0xe339c  ldarg.0
0xe339d  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe33a2  ldarg.0
0xe33a3  ldfld    class System.Windows.Forms.Design.NewItemsContextMenuStrip System.Windows.Forms.Design.ToolStripTemplateNode::contextMenu
0xe33a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem::set_DropDown(class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown)
0xe33ad  ldarg.0
0xe33ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe33b3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem::get_DropDownItems()
0xe33b8  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Layout.ArrangedElementCollection::get_Count()
0xe33bd  ldc.i4.0
0xe33be  ble.s    loc_E3433
0xe33c0  ldarg.0
0xe33c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe33c6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem::get_DropDownItems()
0xe33cb  ldc.i4.0
0xe33cc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(int32)
0xe33d1  castclass System.Windows.Forms.Design.ItemTypeToolStripMenuItem
0xe33d6  stloc.2
0xe33d7  ldarg.0
0xe33d8  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe33dd  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Lime()
0xe33e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_ImageTransparentColor(valuetype [System.Drawing]System.Drawing.Color)
0xe33e7  ldtoken  System.Windows.Forms.Design.ToolStripTemplateNode
0xe33ec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe33f1  ldstr    aToolstriptempl// "ToolStripTemplateNode.bmp"
0xe33f6  call     class [mscorlib]System.IO.Stream System.Drawing.BitmapSelector::GetResourceStream(class [mscorlib]System.Type type, string originalName)
0xe33fb  newobj   instance void [System.Drawing]System.Drawing.Bitmap::.ctor(class [mscorlib]System.IO.Stream)
0xe3400  stloc.3
0xe3401  call     bool System.Windows.Forms.DpiHelper::get_IsScalingRequired()
0xe3406  brfalse.s loc_E341B
0xe3408  ldloc.3
0xe3409  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Lime()
0xe340e  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent(valuetype [System.Drawing]System.Drawing.Color)
0xe3413  ldloca.s 3
0xe3415  ldc.i4.0
0xe3416  call     void System.Windows.Forms.DpiHelper::ScaleBitmapLogicalToDevice(class [System.Drawing]System.Drawing.Bitmap& logicalBitmap, [opt] int32 deviceDpi)
0xe341b  ldarg.0
0xe341c  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe3421  ldloc.3
0xe3422  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItem::set_Image(class [System.Drawing]System.Drawing.Image)
0xe3427  ldarg.0
0xe3428  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe342d  ldloc.2
0xe342e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton::set_DefaultItem(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem)
0xe3433  leave.s  loc_E3444
0xe3435  stloc.s  4
0xe3437  ldloc.s  4
0xe3439  call     bool System.Windows.Forms.ClientUtils::IsCriticalException(class [mscorlib]System.Exception ex)
0xe343e  brfalse.s loc_E3442
0xe3440  rethrow
0xe3442  leave.s  loc_E3444
0xe3444  ldarg.0
0xe3445  ldfld    class TransparentToolStrip System.Windows.Forms.Design.ToolStripTemplateNode::_miniToolStrip
0xe344a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xe344f  ldc.i4.1
0xe3450  newarr   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0xe3455  dup
0xe3456  ldc.i4.0
0xe3457  ldarg.0
0xe3458  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripSplitButton System.Windows.Forms.Design.ToolStripTemplateNode::addItemButton
0xe345d  stelem.ref
0xe345e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::AddRange(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem[])
0xe3463  ret
```
