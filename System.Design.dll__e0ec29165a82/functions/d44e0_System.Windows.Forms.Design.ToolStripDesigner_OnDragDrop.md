# System.Windows.Forms.Design.ToolStripDesigner::OnDragDrop

- ea: `0xd44e0`
- end: `0xd4856`
- name: `System.Windows.Forms.Design.ToolStripDesigner::OnDragDrop`
- size: `886`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task`

## callees

- `0x584f0`
- `0x58ca0`
- `0x8e0b0`
- `0x8eec0`
- `0xa2590`
- `0xa40e0`
- `0xb2d20`
- `0xd2480`
- `0xd24e0`
- `0xd24f0`
- `0xd44e0`
- `0xd8970`
- `0xd8980`
- `0xd8990`
- `0xda8c0`
- `0xdf120`
- `0xe53f0`
- `0x10dd00`

## string_xrefs

- `0xd4635`: `BehaviorServiceMoveControl`
- `0xd463c`: `BehaviorServiceCopyControl`
- `0xd4659`: `BehaviorServiceMoveControls`
- `0xd4660`: `BehaviorServiceCopyControls`

## pseudocode

```c

```

## disassembly

```asm
0xd44e0  ldarg.0
0xd44e1  ldarg.1
0xd44e2  call     instance void System.Windows.Forms.Design.ControlDesigner::OnDragDrop(class [System.Windows.Forms]System.Windows.Forms.DragEventArgs de)
0xd44e7  ldc.i4.0
0xd44e8  stloc.0
0xd44e9  ldarg.0
0xd44ea  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Windows.Forms.Design.ToolStripDesigner::get_ToolStrip()
0xd44ef  stloc.1
0xd44f0  ldarg.1
0xd44f1  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_X()
0xd44f6  ldarg.1
0xd44f7  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Y()
0xd44fc  newobj   instance void POINT::.ctor(int32 x, int32 y)
0xd4501  stloc.2
0xd4502  ldsfld   native int [mscorlib]System.IntPtr::Zero
0xd4507  ldloc.1
0xd4508  callvirt instance native int [System.Windows.Forms]System.Windows.Forms.Control::get_Handle()
0xd450d  ldloc.2
0xd450e  ldc.i4.1
0xd450f  call     int32 System.Design.NativeMethods::MapWindowPoints(native int hWndFrom, native int hWndTo, [in] [out] class POINT pt, int32 cPoints)
0xd4514  pop
0xd4515  ldloca.s 3
0xd4517  ldloc.2
0xd4518  ldfld    int32 POINT::x
0xd451d  ldloc.2
0xd451e  ldfld    int32 POINT::y
0xd4523  call     instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0xd4528  ldarg.0
0xd4529  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Windows.Forms.Design.ToolStripDesigner::get_ToolStrip()
0xd452e  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.Orientation [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Orientation()
0xd4533  brtrue.s loc_D4591
0xd4535  ldarg.0
0xd4536  call     instance class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Windows.Forms.Design.ToolStripDesigner::get_ToolStrip()
0xd453b  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft [System.Windows.Forms]System.Windows.Forms.Control::get_RightToLeft()
0xd4540  ldc.i4.1
0xd4541  bne.un.s loc_D456A
0xd4543  ldloca.s 3
0xd4545  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xd454a  ldloc.1
0xd454b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xd4550  ldc.i4.0
0xd4551  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(int32)
0xd4556  callvirt instance valuetype [System.Drawing]System.Drawing.Rectangle [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Bounds()
0xd455b  stloc.s  5
0xd455d  ldloca.s 5
0xd455f  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_X()
0xd4564  blt.s    loc_D45B6
0xd4566  ldc.i4.1
0xd4567  stloc.0
0xd4568  br.s     loc_D45B6
0xd456a  ldloca.s 3
0xd456c  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0xd4571  ldloc.1
0xd4572  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xd4577  ldc.i4.0
0xd4578  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(int32)
0xd457d  callvirt instance valuetype [System.Drawing]System.Drawing.Rectangle [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Bounds()
0xd4582  stloc.s  5
0xd4584  ldloca.s 5
0xd4586  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_X()
0xd458b  bgt.s    loc_D45B6
0xd458d  ldc.i4.1
0xd458e  stloc.0
0xd458f  br.s     loc_D45B6
0xd4591  ldloca.s 3
0xd4593  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0xd4598  ldloc.1
0xd4599  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xd459e  ldc.i4.0
0xd459f  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::get_Item(int32)
0xd45a4  callvirt instance valuetype [System.Drawing]System.Drawing.Rectangle [System.Windows.Forms]System.Windows.Forms.ToolStripItem::get_Bounds()
0xd45a9  stloc.s  5
0xd45ab  ldloca.s 5
0xd45ad  call     instance int32 [System.Drawing]System.Drawing.Rectangle::get_Y()
0xd45b2  bgt.s    loc_D45B6
0xd45b4  ldc.i4.1
0xd45b5  stloc.0
0xd45b6  ldarg.1
0xd45b7  callvirt instance class [System.Windows.Forms]System.Windows.Forms.IDataObject [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Data()
0xd45bc  isinst   System.Windows.Forms.Design.ToolStripItemDataObject
0xd45c1  stloc.s  4
0xd45c3  ldloc.s  4
0xd45c5  brfalse  loc_D4855
0xd45ca  ldloc.s  4
0xd45cc  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStrip System.Windows.Forms.Design.ToolStripItemDataObject::get_Owner()
0xd45d1  ldloc.1
0xd45d2  bne.un   loc_D4855
0xd45d7  ldloc.s  4
0xd45d9  callvirt instance class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.ToolStripItemDataObject::get_DragComponents()
0xd45de  stloc.s  7
0xd45e0  ldloc.s  4
0xd45e2  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem System.Windows.Forms.Design.ToolStripItemDataObject::get_PrimarySelection()
0xd45e7  stloc.s  8
0xd45e9  ldc.i4.m1
0xd45ea  stloc.s  9
0xd45ec  ldarg.1
0xd45ed  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Effect()
0xd45f2  ldc.i4.1
0xd45f3  ceq
0xd45f5  stloc.s  0xA
0xd45f7  ldloc.s  7
0xd45f9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd45fe  ldc.i4.1
0xd45ff  bne.un.s loc_D4655
0xd4601  ldloc.s  7
0xd4603  ldc.i4.0
0xd4604  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd4609  call     string [System]System.ComponentModel.TypeDescriptor::GetComponentName(object)
0xd460e  stloc.s  0xC
0xd4610  ldloc.s  0xC
0xd4612  brfalse.s loc_D461D
0xd4614  ldloc.s  0xC
0xd4616  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd461b  brtrue.s loc_D4631
0xd461d  ldloc.s  7
0xd461f  ldc.i4.0
0xd4620  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd4625  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xd462a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xd462f  stloc.s  0xC
0xd4631  ldloc.s  0xA
0xd4633  brtrue.s loc_D463C
0xd4635  ldstr    aBehaviorservic// "BehaviorServiceMoveControl"
0xd463a  br.s     loc_D4641
0xd463c  ldstr    aBehaviorservic_0// "BehaviorServiceCopyControl"
0xd4641  ldc.i4.1
0xd4642  newarr   [mscorlib]System.Object
0xd4647  dup
0xd4648  ldc.i4.0
0xd4649  ldloc.s  0xC
0xd464b  stelem.ref
0xd464c  call     string System.Design.SR::GetString(string name, object[] args)
0xd4651  stloc.s  6
0xd4653  br.s     loc_D4681
0xd4655  ldloc.s  0xA
0xd4657  brtrue.s loc_D4660
0xd4659  ldstr    aBehaviorservic_1// "BehaviorServiceMoveControls"
0xd465e  br.s     loc_D4665
0xd4660  ldstr    aBehaviorservic_2// "BehaviorServiceCopyControls"
0xd4665  ldc.i4.1
0xd4666  newarr   [mscorlib]System.Object
0xd466b  dup
0xd466c  ldc.i4.0
0xd466d  ldloc.s  7
0xd466f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd4674  box      [mscorlib]System.Int32
0xd4679  stelem.ref
0xd467a  call     string System.Design.SR::GetString(string name, object[] args)
0xd467f  stloc.s  6
0xd4681  ldarg.0
0xd4682  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.ToolStripDesigner::host
0xd4687  ldloc.s  6
0xd4689  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xd468e  stloc.s  0xB
0xd4690  ldarg.0
0xd4691  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0xd4696  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd469b  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xd46a0  castclass [System]System.ComponentModel.Design.IComponentChangeService
0xd46a5  stloc.s  0xD
0xd46a7  ldloc.s  0xD
0xd46a9  brfalse.s loc_D46C3
0xd46ab  ldloc.s  0xD
0xd46ad  ldloc.1
0xd46ae  ldloc.1
0xd46af  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd46b4  ldstr    aItems// "Items"
0xd46b9  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd46be  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xd46c3  ldloc.s  0xA
0xd46c5  brfalse.s loc_D472C
0xd46c7  ldloc.s  8
0xd46c9  brfalse.s loc_D46D6
0xd46cb  ldloc.s  7
0xd46cd  ldloc.s  8
0xd46cf  callvirt instance int32 [mscorlib]System.Collections.ArrayList::IndexOf(object)
0xd46d4  stloc.s  9
0xd46d6  ldarg.0
0xd46d7  call     instance class System.Windows.Forms.Design.ToolStripKeyboardHandlingService System.Windows.Forms.Design.ToolStripDesigner::get_KeyboardHandlingService()
0xd46dc  brfalse.s loc_D46EA
0xd46de  ldarg.0
0xd46df  call     instance class System.Windows.Forms.Design.ToolStripKeyboardHandlingService System.Windows.Forms.Design.ToolStripDesigner::get_KeyboardHandlingService()
0xd46e4  ldc.i4.1
0xd46e5  callvirt instance void System.Windows.Forms.Design.ToolStripKeyboardHandlingService::set_CopyInProgress(bool value)
0xd46ea  ldloc.s  7
0xd46ec  ldarg.0
0xd46ed  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0xd46f2  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xd46f7  call     class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.DesignerUtils::CopyDragObjects(class [mscorlib]System.Collections.ICollection objects, class [mscorlib]System.IServiceProvider svcProvider)
0xd46fc  isinst   [mscorlib]System.Collections.ArrayList
0xd4701  stloc.s  7
0xd4703  ldarg.0
0xd4704  call     instance class System.Windows.Forms.Design.ToolStripKeyboardHandlingService System.Windows.Forms.Design.ToolStripDesigner::get_KeyboardHandlingService()
0xd4709  brfalse.s loc_D4717
0xd470b  ldarg.0
0xd470c  call     instance class System.Windows.Forms.Design.ToolStripKeyboardHandlingService System.Windows.Forms.Design.ToolStripDesigner::get_KeyboardHandlingService()
0xd4711  ldc.i4.0
0xd4712  callvirt instance void System.Windows.Forms.Design.ToolStripKeyboardHandlingService::set_CopyInProgress(bool value)
0xd4717  ldloc.s  9
0xd4719  ldc.i4.m1
0xd471a  beq.s    loc_D472C
0xd471c  ldloc.s  7
0xd471e  ldloc.s  9
0xd4720  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd4725  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0xd472a  stloc.s  8
0xd472c  ldarg.1
0xd472d  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Effect()
0xd4732  ldc.i4.2
0xd4733  ceq
0xd4735  ldloc.s  0xA
0xd4737  or
0xd4738  brfalse  loc_D47D0
0xd473d  ldc.i4.0
0xd473e  stloc.s  0xF
0xd4740  br.s     loc_D4781
0xd4742  ldloc.0
0xd4743  brfalse.s loc_D4761
0xd4745  ldloc.1
0xd4746  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xd474b  ldc.i4.0
0xd474c  ldloc.s  7
0xd474e  ldloc.s  0xF
0xd4750  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd4755  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0xd475a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::Insert(int32, class [System.Windows.Forms]System.Windows.Forms.ToolStripItem)
0xd475f  br.s     loc_D477B
0xd4761  ldloc.1
0xd4762  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0xd4767  ldloc.s  7
0xd4769  ldloc.s  0xF
0xd476b  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd4770  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0xd4775  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem)
0xd477a  pop
0xd477b  ldloc.s  0xF
0xd477d  ldc.i4.1
0xd477e  add
0xd477f  stloc.s  0xF
0xd4781  ldloc.s  0xF
0xd4783  ldloc.s  7
0xd4785  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd478a  blt.s    loc_D4742
0xd478c  ldloc.s  8
0xd478e  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem
0xd4793  stloc.s  0xE
0xd4795  ldloc.s  0xE
0xd4797  brfalse.s loc_D47B8
0xd4799  ldarg.0
0xd479a  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.ToolStripDesigner::host
0xd479f  ldloc.s  0xE
0xd47a1  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0xd47a6  isinst   System.Windows.Forms.Design.ToolStripMenuItemDesigner
0xd47ab  stloc.s  0x10
0xd47ad  ldloc.s  0x10
0xd47af  brfalse.s loc_D47B8
0xd47b1  ldloc.s  0x10
0xd47b3  callvirt instance void System.Windows.Forms.Design.ToolStripMenuItemDesigner::InitializeDropDown()
0xd47b8  ldarg.0
0xd47b9  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.ToolStripDesigner::get_SelectionService()
0xd47be  ldc.i4.1
0xd47bf  newarr   [System]System.ComponentModel.IComponent
0xd47c4  dup
0xd47c5  ldc.i4.0
0xd47c6  ldloc.s  8
0xd47c8  stelem.ref
0xd47c9  ldc.i4.s 0x12
0xd47cb  callvirt instance void [System]System.ComponentModel.Design.ISelectionService::SetSelectedComponents(class [mscorlib]System.Collections.ICollection, valuetype [System]System.ComponentModel.Design.SelectionTypes)
0xd47d0  ldloc.s  0xD
0xd47d2  brfalse.s loc_D47EE
0xd47d4  ldloc.s  0xD
0xd47d6  ldloc.1
0xd47d7  ldloc.1
0xd47d8  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd47dd  ldstr    aItems// "Items"
0xd47e2  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd47e7  ldnull
0xd47e8  ldnull
0xd47e9  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xd47ee  ldloc.s  0xA
0xd47f0  brfalse.s loc_D4828
0xd47f2  ldloc.s  0xD
0xd47f4  brfalse.s loc_D4828
0xd47f6  ldloc.s  0xD
0xd47f8  ldloc.1
0xd47f9  ldloc.1
0xd47fa  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd47ff  ldstr    aItems// "Items"
0xd4804  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd4809  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xd480e  ldloc.s  0xD
0xd4810  ldloc.1
0xd4811  ldloc.1
0xd4812  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xd4817  ldstr    aItems// "Items"
0xd481c  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xd4821  ldnull
0xd4822  ldnull
0xd4823  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xd4828  ldarg.0
  ... truncated ...
```
