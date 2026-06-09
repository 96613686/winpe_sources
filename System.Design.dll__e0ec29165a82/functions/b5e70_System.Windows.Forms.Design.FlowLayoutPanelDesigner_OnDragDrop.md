# System.Windows.Forms.Design.FlowLayoutPanelDesigner::OnDragDrop

- ea: `0xb5e70`
- end: `0xb6366`
- name: `System.Windows.Forms.Design.FlowLayoutPanelDesigner::OnDragDrop`
- size: `1270`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x584f0`
- `0x58ca0`
- `0x8eec0`
- `0xb2d20`
- `0xb5760`
- `0xb5e70`
- `0xb6e60`
- `0xc2d30`

## string_xrefs

- `0xb5f64`: `BehaviorServiceMoveControl`
- `0xb5f6b`: `BehaviorServiceCopyControl`
- `0xb5f87`: `BehaviorServiceMoveControls`
- `0xb5f8e`: `BehaviorServiceCopyControls`

## pseudocode

```c

```

## disassembly

```asm
0xb5e70  ldc.i4.0
0xb5e71  stloc.0
0xb5e72  ldarg.0
0xb5e73  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb5e78  brfalse.s loc_B5E9C
0xb5e7a  ldarg.0
0xb5e7b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Control System.Windows.Forms.Design.FlowLayoutPanelDesigner::primaryDragControl
0xb5e80  brfalse.s loc_B5E9C
0xb5e82  ldarg.0
0xb5e83  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb5e88  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xb5e8d  ldarg.0
0xb5e8e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Control System.Windows.Forms.Design.FlowLayoutPanelDesigner::primaryDragControl
0xb5e93  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Contains(class [System.Windows.Forms]System.Windows.Forms.Control)
0xb5e98  brfalse.s loc_B5E9C
0xb5e9a  ldc.i4.1
0xb5e9b  stloc.0
0xb5e9c  ldloc.0
0xb5e9d  brtrue.s loc_B5EEB
0xb5e9f  ldarg.0
0xb5ea0  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb5ea5  brfalse.s loc_B5EBE
0xb5ea7  ldarg.0
0xb5ea8  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb5ead  ldarg.0
0xb5eae  ldftn    instance void System.Windows.Forms.Design.FlowLayoutPanelDesigner::OnChildControlAdded(object sender, class [System.Windows.Forms]System.Windows.Forms.ControlEventArgs e)
0xb5eb4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ControlEventHandler::.ctor(object, native int)
0xb5eb9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_ControlAdded(class [System.Windows.Forms]System.Windows.Forms.ControlEventHandler)
0xb5ebe  nop
0xb5ebf  ldarg.0
0xb5ec0  ldarg.1
0xb5ec1  call     instance void System.Windows.Forms.Design.FlowPanelDesigner::OnDragDrop(class [System.Windows.Forms]System.Windows.Forms.DragEventArgs de)
0xb5ec6  leave    loc_B635A
0xb5ecb  ldarg.0
0xb5ecc  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb5ed1  brfalse.s loc_B5EEA
0xb5ed3  ldarg.0
0xb5ed4  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb5ed9  ldarg.0
0xb5eda  ldftn    instance void System.Windows.Forms.Design.FlowLayoutPanelDesigner::OnChildControlAdded(object sender, class [System.Windows.Forms]System.Windows.Forms.ControlEventArgs e)
0xb5ee0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.ControlEventHandler::.ctor(object, native int)
0xb5ee5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::remove_ControlAdded(class [System.Windows.Forms]System.Windows.Forms.ControlEventHandler)
0xb5eea  endfinally
0xb5eeb  ldarg.0
0xb5eec  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xb5ef1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb5ef6  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xb5efb  isinst   [System]System.ComponentModel.Design.IDesignerHost
0xb5f00  stloc.1
0xb5f01  ldloc.1
0xb5f02  brfalse  loc_B635A
0xb5f07  ldnull
0xb5f08  stloc.2
0xb5f09  ldarg.1
0xb5f0a  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects [System.Windows.Forms]System.Windows.Forms.DragEventArgs::get_Effect()
0xb5f0f  ldc.i4.1
0xb5f10  ceq
0xb5f12  stloc.s  4
0xb5f14  ldnull
0xb5f15  stloc.s  5
0xb5f17  ldnull
0xb5f18  stloc.s  6
0xb5f1a  ldarg.0
0xb5f1b  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb5f20  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xb5f25  ldc.i4.1
0xb5f26  bne.un.s loc_B5F83
0xb5f28  ldarg.0
0xb5f29  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb5f2e  ldc.i4.0
0xb5f2f  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xb5f34  call     string [System]System.ComponentModel.TypeDescriptor::GetComponentName(object)
0xb5f39  stloc.s  7
0xb5f3b  ldloc.s  7
0xb5f3d  brfalse.s loc_B5F48
0xb5f3f  ldloc.s  7
0xb5f41  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb5f46  brtrue.s loc_B5F60
0xb5f48  ldarg.0
0xb5f49  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb5f4e  ldc.i4.0
0xb5f4f  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xb5f54  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb5f59  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb5f5e  stloc.s  7
0xb5f60  ldloc.s  4
0xb5f62  brtrue.s loc_B5F6B
0xb5f64  ldstr    aBehaviorservic// "BehaviorServiceMoveControl"
0xb5f69  br.s     loc_B5F70
0xb5f6b  ldstr    aBehaviorservic_0// "BehaviorServiceCopyControl"
0xb5f70  ldc.i4.1
0xb5f71  newarr   [mscorlib]System.Object
0xb5f76  dup
0xb5f77  ldc.i4.0
0xb5f78  ldloc.s  7
0xb5f7a  stelem.ref
0xb5f7b  call     string System.Design.SR::GetString(string name, object[] args)
0xb5f80  stloc.3
0xb5f81  br.s     loc_B5FB2
0xb5f83  ldloc.s  4
0xb5f85  brtrue.s loc_B5F8E
0xb5f87  ldstr    aBehaviorservic_1// "BehaviorServiceMoveControls"
0xb5f8c  br.s     loc_B5F93
0xb5f8e  ldstr    aBehaviorservic_2// "BehaviorServiceCopyControls"
0xb5f93  ldc.i4.1
0xb5f94  newarr   [mscorlib]System.Object
0xb5f99  dup
0xb5f9a  ldc.i4.0
0xb5f9b  ldarg.0
0xb5f9c  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb5fa1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xb5fa6  box      [mscorlib]System.Int32
0xb5fab  stelem.ref
0xb5fac  call     string System.Design.SR::GetString(string name, object[] args)
0xb5fb1  stloc.3
0xb5fb2  ldloc.1
0xb5fb3  ldloc.3
0xb5fb4  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xb5fb9  stloc.2
0xb5fba  br.s     loc_B5FCA
0xb5fbc  ldarg.0
0xb5fbd  ldarg.0
0xb5fbe  ldfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb5fc3  ldc.i4.1
0xb5fc4  add
0xb5fc5  stfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb5fca  ldarg.0
0xb5fcb  ldfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb5fd0  ldarg.0
0xb5fd1  ldfld    valuetype ChildInfo[] System.Windows.Forms.Design.FlowLayoutPanelDesigner::childInfo
0xb5fd6  ldlen
0xb5fd7  conv.i4
0xb5fd8  ldc.i4.1
0xb5fd9  sub
0xb5fda  bge.s    loc_B5FF4
0xb5fdc  ldarg.0
0xb5fdd  ldfld    valuetype ChildInfo[] System.Windows.Forms.Design.FlowLayoutPanelDesigner::childInfo
0xb5fe2  ldarg.0
0xb5fe3  ldfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb5fe8  ldelema  ChildInfo
0xb5fed  ldfld    bool ChildInfo::inSelectionColl
0xb5ff2  brtrue.s loc_B5FBC
0xb5ff4  ldarg.0
0xb5ff5  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0xb5ffa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb5fff  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xb6004  isinst   [System]System.ComponentModel.Design.IComponentChangeService
0xb6009  stloc.s  8
0xb600b  ldarg.0
0xb600c  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb6011  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xb6016  ldstr    aControls// "Controls"
0xb601b  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xb6020  stloc.s  9
0xb6022  ldnull
0xb6023  stloc.s  0xA
0xb6025  ldarg.0
0xb6026  ldfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb602b  ldarg.0
0xb602c  ldfld    valuetype ChildInfo[] System.Windows.Forms.Design.FlowLayoutPanelDesigner::childInfo
0xb6031  ldlen
0xb6032  conv.i4
0xb6033  beq.s    loc_B604F
0xb6035  ldarg.0
0xb6036  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb603b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xb6040  ldarg.0
0xb6041  ldfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb6046  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::get_Item(int32)
0xb604b  stloc.s  0xA
0xb604d  br.s     loc_B6056
0xb604f  ldarg.0
0xb6050  ldc.i4.m1
0xb6051  stfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb6056  ldloc.s  8
0xb6058  brfalse.s loc_B606D
0xb605a  ldloc.s  9
0xb605c  brfalse.s loc_B606D
0xb605e  ldloc.s  8
0xb6060  ldarg.0
0xb6061  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb6066  ldloc.s  9
0xb6068  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xb606d  ldloc.s  4
0xb606f  brtrue.s loc_B60D2
0xb6071  ldc.i4.0
0xb6072  stloc.s  0xB
0xb6074  br.s     loc_B609E
0xb6076  ldarg.0
0xb6077  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb607c  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xb6081  ldarg.0
0xb6082  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb6087  ldloc.s  0xB
0xb6089  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xb608e  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xb6093  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Remove(class [System.Windows.Forms]System.Windows.Forms.Control)
0xb6098  ldloc.s  0xB
0xb609a  ldc.i4.1
0xb609b  add
0xb609c  stloc.s  0xB
0xb609e  ldloc.s  0xB
0xb60a0  ldarg.0
0xb60a1  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb60a6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xb60ab  blt.s    loc_B6076
0xb60ad  ldloc.s  0xA
0xb60af  brfalse  loc_B61BC
0xb60b4  ldarg.0
0xb60b5  ldarg.0
0xb60b6  call     instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel System.Windows.Forms.Design.FlowLayoutPanelDesigner::get_Control()
0xb60bb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xb60c0  ldloc.s  0xA
0xb60c2  ldc.i4.0
0xb60c3  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::GetChildIndex(class [System.Windows.Forms]System.Windows.Forms.Control, bool)
0xb60c8  stfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb60cd  br       loc_B61BC
0xb60d2  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xb60d7  stloc.s  0xC
0xb60d9  ldc.i4.0
0xb60da  stloc.s  0xD
0xb60dc  br.s     loc_B60F9
0xb60de  ldloc.s  0xC
0xb60e0  ldarg.0
0xb60e1  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb60e6  ldloc.s  0xD
0xb60e8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xb60ed  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xb60f2  pop
0xb60f3  ldloc.s  0xD
0xb60f5  ldc.i4.1
0xb60f6  add
0xb60f7  stloc.s  0xD
0xb60f9  ldloc.s  0xD
0xb60fb  ldarg.0
0xb60fc  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb6101  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xb6106  blt.s    loc_B60DE
0xb6108  ldloc.s  0xC
0xb610a  ldarg.0
0xb610b  call     instance class [System]System.ComponentModel.IComponent System.ComponentModel.Design.ComponentDesigner::get_Component()
0xb6110  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0xb6115  call     class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.DesignerUtils::CopyDragObjects(class [mscorlib]System.Collections.ICollection objects, class [mscorlib]System.IServiceProvider svcProvider)
0xb611a  isinst   [mscorlib]System.Collections.ArrayList
0xb611f  stloc.s  0xC
0xb6121  ldloc.s  0xC
0xb6123  brtrue.s loc_B612A
0xb6125  leave    loc_B6365
0xb612a  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xb612f  stloc.s  5
0xb6131  ldc.i4.0
0xb6132  stloc.s  0xE
0xb6134  br.s     loc_B619A
0xb6136  ldloc.s  5
0xb6138  ldarg.0
0xb6139  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb613e  ldloc.s  0xE
0xb6140  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xb6145  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xb614a  pop
0xb614b  ldarg.0
0xb614c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Control System.Windows.Forms.Design.FlowLayoutPanelDesigner::primaryDragControl
0xb6151  ldarg.0
0xb6152  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb6157  ldloc.s  0xE
0xb6159  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xb615e  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xb6163  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xb6168  brfalse.s loc_B617E
0xb616a  ldarg.0
0xb616b  ldloc.s  0xC
0xb616d  ldloc.s  0xE
0xb616f  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xb6174  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xb6179  stfld    class [System.Windows.Forms]System.Windows.Forms.Control System.Windows.Forms.Design.FlowLayoutPanelDesigner::primaryDragControl
0xb617e  ldarg.0
0xb617f  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Forms.Design.FlowLayoutPanelDesigner::dragControls
0xb6184  ldloc.s  0xE
0xb6186  ldloc.s  0xC
0xb6188  ldloc.s  0xE
0xb618a  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xb618f  callvirt instance void [mscorlib]System.Collections.ArrayList::set_Item(int32, object)
0xb6194  ldloc.s  0xE
0xb6196  ldc.i4.1
0xb6197  add
0xb6198  stloc.s  0xE
0xb619a  ldloc.s  0xE
0xb619c  ldloc.s  0xC
0xb619e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xb61a3  blt.s    loc_B6136
0xb61a5  ldarg.0
0xb61a6  ldtoken  [System]System.ComponentModel.Design.ISelectionService
0xb61ab  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb61b0  callvirt instance object System.ComponentModel.Design.ComponentDesigner::GetService(class [mscorlib]System.Type serviceType)
0xb61b5  castclass [System]System.ComponentModel.Design.ISelectionService
0xb61ba  stloc.s  6
0xb61bc  ldarg.0
0xb61bd  ldfld    int32 System.Windows.Forms.Design.FlowLayoutPanelDesigner::insertIndex
0xb61c2  ldc.i4.m1
0xb61c3  bne.un.s loc_B61DB
  ... truncated ...
```
