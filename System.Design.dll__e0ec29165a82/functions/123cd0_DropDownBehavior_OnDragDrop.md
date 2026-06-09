# DropDownBehavior::OnDragDrop

- ea: `0x123cd0`
- end: `0x123fee`
- name: `DropDownBehavior::OnDragDrop`
- size: `798`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x8eec0`
- `0xb2d20`
- `0xd8970`
- `0xd8990`
- `0xda8c0`
- `0xdf100`
- `0xdf120`
- `0xe53f0`
- `0x123cd0`

## string_xrefs

- `0x123d84`: `BehaviorServiceMoveControl`
- `0x123d8b`: `BehaviorServiceCopyControl`
- `0x123da8`: `BehaviorServiceMoveControls`
- `0x123daf`: `BehaviorServiceCopyControls`

## pseudocode

```c

```

## disassembly

```asm
0x123cd0  ldarg.2
0x123cd1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.IDataObject [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Data()
0x123cd6  isinst   System.Windows.Forms.Design.ToolStripItemDataObject
0x123cdb  stloc.0
0x123cdc  ldloc.0
0x123cdd  brfalse  loc_123FED
0x123ce2  ldloc.0
0x123ce3  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem System.Windows.Forms.Design.ToolStripItemDataObject::get_PrimarySelection()
0x123ce8  stloc.1
0x123ce9  ldloc.1
0x123cea  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0x123cef  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x123cf4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x123cf9  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x123cfe  castclass [System]System.ComponentModel.Design.IDesignerHost
0x123d03  stloc.2
0x123d04  ldloc.1
0x123d05  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStrip [System.Windows.Forms]System.Windows.Forms.ToolStripItem::GetCurrentParent()
0x123d0a  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown
0x123d0f  stloc.3
0x123d10  ldnull
0x123d11  stloc.s  4
0x123d13  ldloc.3
0x123d14  brfalse.s loc_123D23
0x123d16  ldloc.3
0x123d17  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItem [System.Windows.Forms]System.Windows.Forms.ToolStripDropDown::get_OwnerItem()
0x123d1c  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem
0x123d21  stloc.s  4
0x123d23  ldloc.s  4
0x123d25  brfalse  loc_123FED
0x123d2a  ldloc.2
0x123d2b  brfalse  loc_123FED
0x123d30  ldloc.0
0x123d31  callvirt instance class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.ToolStripItemDataObject::get_DragComponents()
0x123d36  stloc.s  6
0x123d38  ldc.i4.m1
0x123d39  stloc.s  7
0x123d3b  ldarg.2
0x123d3c  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Effect()
0x123d41  ldc.i4.1
0x123d42  ceq
0x123d44  stloc.s  8
0x123d46  ldloc.s  6
0x123d48  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x123d4d  ldc.i4.1
0x123d4e  bne.un.s loc_123DA4
0x123d50  ldloc.s  6
0x123d52  ldc.i4.0
0x123d53  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x123d58  call     string [System]System.ComponentModel.TypeDescriptor::GetComponentName(object)
0x123d5d  stloc.s  0xA
0x123d5f  ldloc.s  0xA
0x123d61  brfalse.s loc_123D6C
0x123d63  ldloc.s  0xA
0x123d65  callvirt instance int32 [mscorlib]System.String::get_Length()
0x123d6a  brtrue.s loc_123D80
0x123d6c  ldloc.s  6
0x123d6e  ldc.i4.0
0x123d6f  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x123d74  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x123d79  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x123d7e  stloc.s  0xA
0x123d80  ldloc.s  8
0x123d82  brtrue.s loc_123D8B
0x123d84  ldstr    aBehaviorservic// "BehaviorServiceMoveControl"
0x123d89  br.s     loc_123D90
0x123d8b  ldstr    aBehaviorservic_0// "BehaviorServiceCopyControl"
0x123d90  ldc.i4.1
0x123d91  newarr   [mscorlib]System.Object
0x123d96  dup
0x123d97  ldc.i4.0
0x123d98  ldloc.s  0xA
0x123d9a  stelem.ref
0x123d9b  call     string System.Design.SR::GetString(string name, object[] args)
0x123da0  stloc.s  5
0x123da2  br.s     loc_123DD0
0x123da4  ldloc.s  8
0x123da6  brtrue.s loc_123DAF
0x123da8  ldstr    aBehaviorservic_1// "BehaviorServiceMoveControls"
0x123dad  br.s     loc_123DB4
0x123daf  ldstr    aBehaviorservic_2// "BehaviorServiceCopyControls"
0x123db4  ldc.i4.1
0x123db5  newarr   [mscorlib]System.Object
0x123dba  dup
0x123dbb  ldc.i4.0
0x123dbc  ldloc.s  6
0x123dbe  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x123dc3  box      [mscorlib]System.Int32
0x123dc8  stelem.ref
0x123dc9  call     string System.Design.SR::GetString(string name, object[] args)
0x123dce  stloc.s  5
0x123dd0  ldloc.2
0x123dd1  ldloc.s  5
0x123dd3  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x123dd8  stloc.s  9
0x123dda  ldloc.1
0x123ddb  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0x123de0  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0x123de5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x123dea  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x123def  castclass [System]System.ComponentModel.Design.IComponentChangeService
0x123df4  stloc.s  0xB
0x123df6  ldloc.s  0xB
0x123df8  brfalse.s loc_123E14
0x123dfa  ldloc.s  0xB
0x123dfc  ldloc.s  4
0x123dfe  ldloc.s  4
0x123e00  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x123e05  ldstr    aDropdownitems// "DropDownItems"
0x123e0a  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x123e0f  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0x123e14  ldloc.s  8
0x123e16  brfalse.s loc_123E81
0x123e18  ldloc.1
0x123e19  brfalse.s loc_123E25
0x123e1b  ldloc.s  6
0x123e1d  ldloc.1
0x123e1e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::IndexOf(object)
0x123e23  stloc.s  7
0x123e25  ldloc.1
0x123e26  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0x123e2b  ldtoken  System.Windows.Forms.Design.ToolStripKeyboardHandlingService
0x123e30  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x123e35  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x123e3a  castclass System.Windows.Forms.Design.ToolStripKeyboardHandlingService
0x123e3f  stloc.s  0xD
0x123e41  ldloc.s  0xD
0x123e43  brfalse.s loc_123E4D
0x123e45  ldloc.s  0xD
0x123e47  ldc.i4.1
0x123e48  callvirt instance void System.Windows.Forms.Design.ToolStripKeyboardHandlingService::set_CopyInProgress(bool value)
0x123e4d  ldloc.s  6
0x123e4f  ldloc.1
0x123e50  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0x123e55  call     class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.DesignerUtils::CopyDragObjects(class [mscorlib]System.Collections.ICollection objects, class [mscorlib]System.IServiceProvider svcProvider)
0x123e5a  isinst   [mscorlib]System.Collections.ArrayList
0x123e5f  stloc.s  6
0x123e61  ldloc.s  0xD
0x123e63  brfalse.s loc_123E6D
0x123e65  ldloc.s  0xD
0x123e67  ldc.i4.0
0x123e68  callvirt instance void System.Windows.Forms.Design.ToolStripKeyboardHandlingService::set_CopyInProgress(bool value)
0x123e6d  ldloc.s  7
0x123e6f  ldc.i4.m1
0x123e70  beq.s    loc_123E81
0x123e72  ldloc.s  6
0x123e74  ldloc.s  7
0x123e76  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x123e7b  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0x123e80  stloc.1
0x123e81  ldarg.2
0x123e82  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Effect()
0x123e87  ldc.i4.2
0x123e88  ceq
0x123e8a  ldloc.s  8
0x123e8c  or
0x123e8d  brfalse  loc_123F1B
0x123e92  ldloc.s  6
0x123e94  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x123e99  stloc.s  0xF
0x123e9b  br.s     loc_123EB9
0x123e9d  ldloc.s  0xF
0x123e9f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x123ea4  castclass [System.Windows.Forms]System.Windows.Forms.ToolStripItem
0x123ea9  stloc.s  0x10
0x123eab  ldloc.3
0x123eac  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection [System.Windows.Forms]System.Windows.Forms.ToolStrip::get_Items()
0x123eb1  ldloc.s  0x10
0x123eb3  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ToolStripItemCollection::Add(class [System.Windows.Forms]System.Windows.Forms.ToolStripItem)
0x123eb8  pop
0x123eb9  ldloc.s  0xF
0x123ebb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x123ec0  brtrue.s loc_123E9D
0x123ec2  leave.s  loc_123ED9
0x123ec4  ldloc.s  0xF
0x123ec6  isinst   [mscorlib]System.IDisposable
0x123ecb  stloc.s  0x11
0x123ecd  ldloc.s  0x11
0x123ecf  brfalse.s loc_123ED8
0x123ed1  ldloc.s  0x11
0x123ed3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x123ed8  endfinally
0x123ed9  ldloc.1
0x123eda  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem
0x123edf  stloc.s  0xE
0x123ee1  ldloc.s  0xE
0x123ee3  brfalse.s loc_123EFF
0x123ee5  ldloc.2
0x123ee6  ldloc.s  0xE
0x123ee8  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x123eed  isinst   System.Windows.Forms.Design.ToolStripMenuItemDesigner
0x123ef2  stloc.s  0x12
0x123ef4  ldloc.s  0x12
0x123ef6  brfalse.s loc_123EFF
0x123ef8  ldloc.s  0x12
0x123efa  callvirt instance void System.Windows.Forms.Design.ToolStripMenuItemDesigner::InitializeDropDown()
0x123eff  ldarg.0
0x123f00  ldfld    class System.Windows.Forms.Design.ToolStripMenuItemDesigner DropDownBehavior::menuItemDesigner
0x123f05  ldfld    class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.ToolStripMenuItemDesigner::selSvc
0x123f0a  ldc.i4.1
0x123f0b  newarr   [System]System.ComponentModel.IComponent
0x123f10  dup
0x123f11  ldc.i4.0
0x123f12  ldloc.1
0x123f13  stelem.ref
0x123f14  ldc.i4.s 0x12
0x123f16  callvirt instance void [System]System.ComponentModel.Design.ISelectionService::SetSelectedComponents(class [mscorlib]System.Collections.ICollection, valuetype [System]System.ComponentModel.Design.SelectionTypes)
0x123f1b  ldloc.s  0xB
0x123f1d  brfalse.s loc_123F3B
0x123f1f  ldloc.s  0xB
0x123f21  ldloc.s  4
0x123f23  ldloc.s  4
0x123f25  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x123f2a  ldstr    aDropdownitems// "DropDownItems"
0x123f2f  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x123f34  ldnull
0x123f35  ldnull
0x123f36  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0x123f3b  ldloc.s  8
0x123f3d  brfalse.s loc_123F79
0x123f3f  ldloc.s  0xB
0x123f41  brfalse.s loc_123F79
0x123f43  ldloc.s  0xB
0x123f45  ldloc.s  4
0x123f47  ldloc.s  4
0x123f49  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x123f4e  ldstr    aDropdownitems// "DropDownItems"
0x123f53  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x123f58  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0x123f5d  ldloc.s  0xB
0x123f5f  ldloc.s  4
0x123f61  ldloc.s  4
0x123f63  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x123f68  ldstr    aDropdownitems// "DropDownItems"
0x123f6d  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x123f72  ldnull
0x123f73  ldnull
0x123f74  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0x123f79  ldloc.s  4
0x123f7b  brfalse.s loc_123FA4
0x123f7d  ldloc.2
0x123f7e  ldloc.s  4
0x123f80  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x123f85  isinst   System.Windows.Forms.Design.ToolStripMenuItemDesigner
0x123f8a  stloc.s  0x13
0x123f8c  ldloc.s  0x13
0x123f8e  brfalse.s loc_123FA4
0x123f90  ldloc.s  0x13
0x123f92  ldc.i4.0
0x123f93  ldloc.s  4
0x123f95  callvirt instance void System.Windows.Forms.Design.ToolStripMenuItemDesigner::InitializeBodyGlyphsForItems(bool addGlyphs, class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem item)
0x123f9a  ldloc.s  0x13
0x123f9c  ldc.i4.1
0x123f9d  ldloc.s  4
0x123f9f  callvirt instance void System.Windows.Forms.Design.ToolStripMenuItemDesigner::InitializeBodyGlyphsForItems(bool addGlyphs, class [System.Windows.Forms]System.Windows.Forms.ToolStripDropDownItem item)
0x123fa4  ldloc.1
0x123fa5  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0x123faa  ldtoken  System.Windows.Forms.Design.Behavior.BehaviorService
0x123faf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x123fb4  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x123fb9  castclass System.Windows.Forms.Design.Behavior.BehaviorService
0x123fbe  stloc.s  0xC
0x123fc0  ldloc.s  0xC
0x123fc2  brfalse.s loc_123FCB
0x123fc4  ldloc.s  0xC
0x123fc6  callvirt instance void System.Windows.Forms.Design.Behavior.BehaviorService::SyncSelection()
0x123fcb  leave.s  loc_123FED
0x123fcd  pop
0x123fce  ldloc.s  9
0x123fd0  brfalse.s loc_123FDC
0x123fd2  ldloc.s  9
0x123fd4  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Cancel()
0x123fd9  ldnull
0x123fda  stloc.s  9
0x123fdc  leave.s  loc_123FED
0x123fde  ldloc.s  9
0x123fe0  brfalse.s loc_123FE9
0x123fe2  ldloc.s  9
0x123fe4  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0x123fe9  ldnull
0x123fea  stloc.s  9
0x123fec  endfinally
0x123fed  ret
```
