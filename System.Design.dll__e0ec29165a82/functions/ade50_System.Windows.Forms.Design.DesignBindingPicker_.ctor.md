# System.Windows.Forms.Design.DesignBindingPicker::.ctor

- ea: `0xade50`
- end: `0xae26c`
- name: `System.Windows.Forms.Design.DesignBindingPicker::.ctor`
- size: `1052`
- prototype: ``
- caller_count: `9`
- callee_count: `11`
- tags: ``

## callers

- `0x97070`
- `0xa6840`
- `0xa6bf0`
- `0xab910`
- `0xad680`
- `0xad740`
- `0xad9d0`
- `0xaddd0`
- `0xbb5d0`

## callees

- `0x8ef40`
- `0x8f6c0`
- `0x8f730`
- `0x8f740`
- `0x8f780`
- `0xade50`
- `0xb2f80`
- `0xef2e0`
- `0x1186e0`
- `0x118710`
- `0x118730`

## string_xrefs

- `0xadf3f`: `DesignBindingPickerTreeViewAccessibleName`
- `0xae250`: `DesignBindingPickerAccessibleName`

## pseudocode

```c

```

## disassembly

```asm
0xade50  ldarg.0
0xade51  newobj   instance void [System.Windows.Forms]System.Windows.Forms.BindingContext::.ctor()
0xade56  stfld    class [System.Windows.Forms]System.Windows.Forms.BindingContext System.Windows.Forms.Design.DesignBindingPicker::bindingContext
0xade5b  ldarg.0
0xade5c  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::.ctor()
0xade61  ldarg.0
0xade62  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xade67  ldsfld   bool System.Windows.Forms.Design.DesignBindingPicker::isScalingInitialized
0xade6c  brtrue.s loc_ADE99
0xade6e  call     bool System.Windows.Forms.DpiHelper::get_IsScalingRequired()
0xade73  brfalse.s loc_ADE93
0xade75  ldc.i4   0xFA
0xade7a  call     int32 System.Windows.Forms.DpiHelper::LogicalToDeviceUnitsY(int32 value)
0xade7f  stsfld   int32 System.Windows.Forms.Design.DesignBindingPicker::minimumHeight
0xade84  ldc.i4   0xFA
0xade89  call     int32 System.Windows.Forms.DpiHelper::LogicalToDeviceUnitsX(int32 value)
0xade8e  stsfld   int32 System.Windows.Forms.Design.DesignBindingPicker::minimumWidth
0xade93  ldc.i4.1
0xade94  stsfld   bool System.Windows.Forms.Design.DesignBindingPicker::isScalingInitialized
0xade99  ldarg.0
0xade9a  newobj   instance void BindingPickerTree::.ctor()
0xade9f  stfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadea4  ldarg.0
0xadea5  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadeaa  ldc.i4.1
0xadeab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_HotTracking(bool)
0xadeb0  ldarg.0
0xadeb1  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadeb6  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0xadebb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xadec0  ldarg.0
0xadec1  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadec6  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_WindowText()
0xadecb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0xaded0  ldarg.0
0xaded1  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xaded6  ldc.i4.0
0xaded7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::set_BorderStyle(valuetype [System.Windows.Forms]System.Windows.Forms.BorderStyle)
0xadedc  ldarg.0
0xadedd  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadee2  callvirt instance valuetype [System.Drawing]System.Drawing.Size [System.Windows.Forms]System.Windows.Forms.Control::get_Size()
0xadee7  stloc.0
0xadee8  ldarg.0
0xadee9  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadeee  ldc.i4.5
0xadeef  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xadef4  ldarg.0
0xadef5  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadefa  ldarg.0
0xadefb  ldftn    instance void System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl_MouseMove(object sender, class [System.Windows.Forms]System.Windows.Forms.MouseEventArgs e)
0xadf01  newobj   instance void [System.Windows.Forms]System.Windows.Forms.MouseEventHandler::.ctor(object, native int)
0xadf06  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_MouseMove(class [System.Windows.Forms]System.Windows.Forms.MouseEventHandler)
0xadf0b  ldarg.0
0xadf0c  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadf11  ldarg.0
0xadf12  ldftn    instance void System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl_MouseLeave(object sender, class [mscorlib]System.EventArgs e)
0xadf18  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xadf1d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_MouseLeave(class [mscorlib]System.EventHandler)
0xadf22  ldarg.0
0xadf23  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadf28  ldarg.0
0xadf29  ldftn    instance void System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl_AfterExpand(object sender, class [System.Windows.Forms]System.Windows.Forms.TreeViewEventArgs tvcevent)
0xadf2f  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler::.ctor(object, native int)
0xadf34  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TreeView::add_AfterExpand(class [System.Windows.Forms]System.Windows.Forms.TreeViewEventHandler)
0xadf39  ldarg.0
0xadf3a  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadf3f  ldstr    aDesignbindingp// "DesignBindingPickerTreeViewAccessibleNa"...
0xadf44  call     string System.Design.SR::GetString(string name)
0xadf49  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xadf4e  ldarg.0
0xadf4f  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xadf54  call     void System.Windows.Forms.Design.DesignerUtils::ApplyTreeViewThemeStyles(class [System.Windows.Forms]System.Windows.Forms.TreeView treeView)
0xadf59  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xadf5e  stloc.1
0xadf5f  ldloc.1
0xadf60  ldc.i4.1
0xadf61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0xadf66  ldloc.1
0xadf67  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlDark()
0xadf6c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xadf71  ldloc.1
0xadf72  ldc.i4.1
0xadf73  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xadf78  ldarg.0
0xadf79  newobj   instance void BindingPickerLink::.ctor()
0xadf7e  stfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadf83  ldarg.0
0xadf84  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadf89  ldstr    aDesignbindingp_0// "DesignBindingPickerAddProjDataSourceLab"...
0xadf8e  call     string System.Design.SR::GetString(string name)
0xadf93  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xadf98  ldarg.0
0xadf99  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadf9e  ldc.i4.s 0x10
0xadfa0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xadfa5  ldarg.0
0xadfa6  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadfab  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0xadfb0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xadfb5  ldarg.0
0xadfb6  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadfbb  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_WindowText()
0xadfc0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0xadfc5  ldarg.0
0xadfc6  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadfcb  ldc.i4.2
0xadfcc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::set_LinkBehavior(valuetype [System.Windows.Forms]System.Windows.Forms.LinkBehavior)
0xadfd1  ldarg.0
0xadfd2  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadfd7  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0xadfdc  stloc.2
0xadfdd  ldarg.0
0xadfde  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadfe3  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0xadfe8  stloc.3
0xadfe9  ldarg.0
0xadfea  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadfef  ldc.i4.5
0xadff0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xadff5  ldarg.0
0xadff6  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xadffb  ldarg.0
0xadffc  ldftn    instance void System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl_Click(object sender, class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventArgs e)
0xae002  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler::.ctor(object, native int)
0xae007  callvirt instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::add_LinkClicked(class [System.Windows.Forms]System.Windows.Forms.LinkLabelLinkClickedEventHandler)
0xae00c  ldtoken  System.Windows.Forms.Design.DesignBindingPicker
0xae011  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xae016  ldstr    aAddnewdatasour// "AddNewDataSource.bmp"
0xae01b  call     class [mscorlib]System.IO.Stream System.Drawing.BitmapSelector::GetResourceStream(class [mscorlib]System.Type type, string originalName)
0xae020  newobj   instance void [System.Drawing]System.Drawing.Bitmap::.ctor(class [mscorlib]System.IO.Stream)
0xae025  stloc.s  4
0xae027  ldloc.s  4
0xae029  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Magenta()
0xae02e  callvirt instance void [System.Drawing]System.Drawing.Bitmap::MakeTransparent(valuetype [System.Drawing]System.Drawing.Color)
0xae033  call     bool System.Windows.Forms.DpiHelper::get_IsScalingRequired()
0xae038  brfalse.s loc_AE064
0xae03a  ldloca.s 4
0xae03c  ldc.i4.0
0xae03d  call     void System.Windows.Forms.DpiHelper::ScaleBitmapLogicalToDevice(class [System.Drawing]System.Drawing.Bitmap& logicalBitmap, [opt] int32 deviceDpi)
0xae042  ldarg.0
0xae043  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xae048  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0xae04d  call     int32 System.Windows.Forms.DpiHelper::LogicalToDeviceUnitsY(int32 value)
0xae052  stloc.2
0xae053  ldarg.0
0xae054  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xae059  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0xae05e  call     int32 System.Windows.Forms.DpiHelper::LogicalToDeviceUnitsX(int32 value)
0xae063  stloc.3
0xae064  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0xae069  stloc.s  5
0xae06b  ldloc.s  5
0xae06d  ldloc.s  4
0xae06f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0xae074  ldloc.s  5
0xae076  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0xae07b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xae080  ldloc.s  5
0xae082  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_WindowText()
0xae087  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0xae08c  ldloc.s  5
0xae08e  ldloc.3
0xae08f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Width(int32)
0xae094  ldloc.s  5
0xae096  ldloc.2
0xae097  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0xae09c  ldloc.s  5
0xae09e  ldc.i4.3
0xae09f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xae0a4  ldloc.s  5
0xae0a6  ldc.i4.3
0xae0a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0xae0ac  ldloc.s  5
0xae0ae  ldc.i4.s 0x28
0xae0b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleRole(valuetype [System.Windows.Forms]System.Windows.Forms.AccessibleRole)
0xae0b5  ldarg.0
0xae0b6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0xae0bb  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::addNewPanel
0xae0c0  ldarg.0
0xae0c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::addNewPanel
0xae0c6  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xae0cb  ldarg.0
0xae0cc  ldfld    class BindingPickerLink System.Windows.Forms.Design.DesignBindingPicker::addNewCtrl
0xae0d1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae0d6  ldarg.0
0xae0d7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::addNewPanel
0xae0dc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xae0e1  ldloc.s  5
0xae0e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae0e8  ldarg.0
0xae0e9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::addNewPanel
0xae0ee  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xae0f3  ldloc.1
0xae0f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae0f9  ldarg.0
0xae0fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::addNewPanel
0xae0ff  ldloc.2
0xae100  ldc.i4.1
0xae101  add
0xae102  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0xae107  ldarg.0
0xae108  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::addNewPanel
0xae10d  ldc.i4.2
0xae10e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xae113  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xae118  stloc.s  6
0xae11a  ldloc.s  6
0xae11c  ldc.i4.1
0xae11d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0xae122  ldloc.s  6
0xae124  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_ControlDark()
0xae129  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xae12e  ldloc.s  6
0xae130  ldc.i4.1
0xae131  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xae136  ldarg.0
0xae137  newobj   instance void HelpTextLabel::.ctor()
0xae13c  stfld    class HelpTextLabel System.Windows.Forms.Design.DesignBindingPicker::helpTextCtrl
0xae141  ldarg.0
0xae142  ldfld    class HelpTextLabel System.Windows.Forms.Design.DesignBindingPicker::helpTextCtrl
0xae147  ldc.i4.1
0xae148  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xae14d  ldarg.0
0xae14e  ldfld    class HelpTextLabel System.Windows.Forms.Design.DesignBindingPicker::helpTextCtrl
0xae153  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0xae158  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xae15d  ldarg.0
0xae15e  ldfld    class HelpTextLabel System.Windows.Forms.Design.DesignBindingPicker::helpTextCtrl
0xae163  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_WindowText()
0xae168  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ForeColor(valuetype [System.Drawing]System.Drawing.Color)
0xae16d  ldarg.0
0xae16e  ldfld    class HelpTextLabel System.Windows.Forms.Design.DesignBindingPicker::helpTextCtrl
0xae173  dup
0xae174  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0xae179  ldc.i4.2
0xae17a  mul
0xae17b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0xae180  ldarg.0
0xae181  ldfld    class HelpTextLabel System.Windows.Forms.Design.DesignBindingPicker::helpTextCtrl
0xae186  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Height()
0xae18b  stloc.s  7
0xae18d  call     bool System.Windows.Forms.DpiHelper::get_IsScalingRequired()
0xae192  brfalse.s loc_AE19D
0xae194  ldloc.s  7
0xae196  call     int32 System.Windows.Forms.DpiHelper::LogicalToDeviceUnitsY(int32 value)
0xae19b  stloc.s  7
0xae19d  ldarg.0
0xae19e  ldfld    class HelpTextLabel System.Windows.Forms.Design.DesignBindingPicker::helpTextCtrl
0xae1a3  ldc.i4.5
0xae1a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xae1a9  ldarg.0
0xae1aa  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Panel::.ctor()
0xae1af  stfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::helpTextPanel
0xae1b4  ldarg.0
0xae1b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::helpTextPanel
0xae1ba  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xae1bf  ldarg.0
0xae1c0  ldfld    class HelpTextLabel System.Windows.Forms.Design.DesignBindingPicker::helpTextCtrl
0xae1c5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae1ca  ldarg.0
0xae1cb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::helpTextPanel
0xae1d0  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xae1d5  ldloc.s  6
0xae1d7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae1dc  ldarg.0
0xae1dd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::helpTextPanel
0xae1e2  ldloc.s  7
0xae1e4  ldc.i4.1
0xae1e5  add
0xae1e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Height(int32)
0xae1eb  ldarg.0
0xae1ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::helpTextPanel
0xae1f1  ldc.i4.2
0xae1f2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xae1f7  ldarg.0
0xae1f8  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xae1fd  ldarg.0
0xae1fe  ldfld    class BindingPickerTree System.Windows.Forms.Design.DesignBindingPicker::treeViewCtrl
0xae203  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae208  ldarg.0
0xae209  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xae20e  ldarg.0
0xae20f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::addNewPanel
0xae214  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae219  ldarg.0
0xae21a  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xae21f  ldarg.0
0xae220  ldfld    class [System.Windows.Forms]System.Windows.Forms.Panel System.Windows.Forms.Design.DesignBindingPicker::helpTextPanel
0xae225  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xae22a  ldarg.0
0xae22b  ldc.i4.0
0xae22c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0xae231  ldarg.0
0xae232  ldloc.0
0xae233  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xae238  ldarg.0
0xae239  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0xae23e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xae243  ldarg.0
0xae244  ldarg.0
  ... truncated ...
```
