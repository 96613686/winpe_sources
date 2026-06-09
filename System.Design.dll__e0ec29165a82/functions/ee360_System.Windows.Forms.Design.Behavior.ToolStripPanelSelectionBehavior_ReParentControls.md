# System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionBehavior::ReParentControls

- ea: `0xee360`
- end: `0xee5c5`
- name: `System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionBehavior::ReParentControls`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0xee5d0`

## callees

- `0x8eec0`
- `0xb2d20`
- `0xee360`

## string_xrefs

- `0xee3d1`: `BehaviorServiceMoveControl`
- `0xee3d8`: `BehaviorServiceCopyControl`
- `0xee3f2`: `BehaviorServiceMoveControls`
- `0xee3f9`: `BehaviorServiceCopyControls`

## pseudocode

```c

```

## disassembly

```asm
0xee360  ldarg.0
0xee361  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionBehavior::serviceProvider
0xee366  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xee36b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xee370  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xee375  isinst   [System]System.ComponentModel.Design.IDesignerHost
0xee37a  stloc.0
0xee37b  ldloc.0
0xee37c  brfalse  loc_EE5C4
0xee381  ldarg.1
0xee382  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xee387  ldc.i4.0
0xee388  ble      loc_EE5C4
0xee38d  ldarg.1
0xee38e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xee393  ldc.i4.1
0xee394  bne.un.s loc_EE3EF
0xee396  ldarg.1
0xee397  ldc.i4.0
0xee398  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xee39d  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStrip
0xee3a2  brfalse.s loc_EE3EF
0xee3a4  ldarg.1
0xee3a5  ldc.i4.0
0xee3a6  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xee3ab  call     string [System]System.ComponentModel.TypeDescriptor::GetComponentName(object)
0xee3b0  stloc.3
0xee3b1  ldloc.3
0xee3b2  brfalse.s loc_EE3BC
0xee3b4  ldloc.3
0xee3b5  callvirt instance int32 [mscorlib]System.String::get_Length()
0xee3ba  brtrue.s loc_EE3CE
0xee3bc  ldarg.1
0xee3bd  ldc.i4.0
0xee3be  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xee3c3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xee3c8  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xee3cd  stloc.3
0xee3ce  ldarg.2
0xee3cf  brtrue.s loc_EE3D8
0xee3d1  ldstr    aBehaviorservic// "BehaviorServiceMoveControl"
0xee3d6  br.s     loc_EE3DD
0xee3d8  ldstr    aBehaviorservic_0// "BehaviorServiceCopyControl"
0xee3dd  ldc.i4.1
0xee3de  newarr   [mscorlib]System.Object
0xee3e3  dup
0xee3e4  ldc.i4.0
0xee3e5  ldloc.3
0xee3e6  stelem.ref
0xee3e7  call     string System.Design.SR::GetString(string name, object[] args)
0xee3ec  stloc.1
0xee3ed  br.s     loc_EE418
0xee3ef  ldarg.2
0xee3f0  brtrue.s loc_EE3F9
0xee3f2  ldstr    aBehaviorservic_1// "BehaviorServiceMoveControls"
0xee3f7  br.s     loc_EE3FE
0xee3f9  ldstr    aBehaviorservic_2// "BehaviorServiceCopyControls"
0xee3fe  ldc.i4.1
0xee3ff  newarr   [mscorlib]System.Object
0xee404  dup
0xee405  ldc.i4.0
0xee406  ldarg.1
0xee407  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xee40c  box      [mscorlib]System.Int32
0xee411  stelem.ref
0xee412  call     string System.Design.SR::GetString(string name, object[] args)
0xee417  stloc.1
0xee418  ldloc.0
0xee419  ldloc.1
0xee41a  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xee41f  stloc.2
0xee420  ldnull
0xee421  stloc.s  4
0xee423  ldarg.0
0xee424  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionBehavior::serviceProvider
0xee429  ldtoken  [System]System.ComponentModel.Design.ISelectionService
0xee42e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xee433  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xee438  castclass [System]System.ComponentModel.Design.ISelectionService
0xee43d  stloc.s  5
0xee43f  ldarg.2
0xee440  brfalse.s loc_EE465
0xee442  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xee447  stloc.s  4
0xee449  ldarg.0
0xee44a  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionBehavior::serviceProvider
0xee44f  ldtoken  [System]System.ComponentModel.Design.ISelectionService
0xee454  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xee459  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xee45e  castclass [System]System.ComponentModel.Design.ISelectionService
0xee463  stloc.s  5
0xee465  ldc.i4.0
0xee466  stloc.s  6
0xee468  br       loc_EE59B
0xee46d  ldarg.1
0xee46e  ldloc.s  6
0xee470  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xee475  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xee47a  stloc.s  7
0xee47c  ldloc.s  7
0xee47e  isinst   [System.Windows.Forms]System.Windows.Forms.ToolStrip
0xee483  brfalse  loc_EE595
0xee488  ldarg.2
0xee489  brfalse.s loc_EE4CB
0xee48b  ldloc.s  4
0xee48d  callvirt instance void [mscorlib]System.Collections.ArrayList::Clear()
0xee492  ldloc.s  4
0xee494  ldloc.s  7
0xee496  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xee49b  pop
0xee49c  ldloc.s  4
0xee49e  ldarg.0
0xee49f  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionBehavior::serviceProvider
0xee4a4  call     class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.DesignerUtils::CopyDragObjects(class [mscorlib]System.Collections.ICollection objects, class [mscorlib]System.IServiceProvider svcProvider)
0xee4a9  isinst   [mscorlib]System.Collections.ArrayList
0xee4ae  stloc.s  4
0xee4b0  ldloc.s  4
0xee4b2  brfalse.s loc_EE4CB
0xee4b4  ldloc.s  4
0xee4b6  ldc.i4.0
0xee4b7  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xee4bc  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xee4c1  stloc.s  7
0xee4c3  ldloc.s  7
0xee4c5  ldc.i4.1
0xee4c6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xee4cb  ldarg.0
0xee4cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.ToolStripPanel System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionBehavior::relatedControl
0xee4d1  stloc.s  8
0xee4d3  ldarg.0
0xee4d4  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.ToolStripPanelSelectionBehavior::serviceProvider
0xee4d9  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0xee4de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xee4e3  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xee4e8  isinst   [System]System.ComponentModel.Design.IComponentChangeService
0xee4ed  stloc.s  9
0xee4ef  ldloc.s  8
0xee4f1  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xee4f6  ldstr    aControls// "Controls"
0xee4fb  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xee500  stloc.s  0xA
0xee502  ldloc.s  7
0xee504  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0xee509  stloc.s  0xB
0xee50b  ldloc.s  0xB
0xee50d  brfalse.s loc_EE52F
0xee50f  ldarg.2
0xee510  brtrue.s loc_EE52F
0xee512  ldloc.s  9
0xee514  brfalse.s loc_EE521
0xee516  ldloc.s  9
0xee518  ldloc.s  0xB
0xee51a  ldloc.s  0xA
0xee51c  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xee521  ldloc.s  0xB
0xee523  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xee528  ldloc.s  7
0xee52a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Remove(class [System.Windows.Forms]System.Windows.Forms.Control)
0xee52f  ldloc.s  9
0xee531  brfalse.s loc_EE53E
0xee533  ldloc.s  9
0xee535  ldloc.s  8
0xee537  ldloc.s  0xA
0xee539  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0xee53e  ldloc.s  8
0xee540  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xee545  ldloc.s  7
0xee547  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xee54c  ldloc.s  9
0xee54e  brfalse.s loc_EE564
0xee550  ldloc.s  0xB
0xee552  brfalse.s loc_EE564
0xee554  ldarg.2
0xee555  brtrue.s loc_EE564
0xee557  ldloc.s  9
0xee559  ldloc.s  0xB
0xee55b  ldloc.s  0xA
0xee55d  ldnull
0xee55e  ldnull
0xee55f  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xee564  ldloc.s  9
0xee566  brfalse.s loc_EE575
0xee568  ldloc.s  9
0xee56a  ldloc.s  8
0xee56c  ldloc.s  0xA
0xee56e  ldnull
0xee56f  ldnull
0xee570  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanged(object, class [System]System.ComponentModel.MemberDescriptor, object, object)
0xee575  ldloc.s  5
0xee577  brfalse.s loc_EE595
0xee579  ldloc.s  5
0xee57b  ldc.i4.1
0xee57c  newarr   [mscorlib]System.Object
0xee581  dup
0xee582  ldc.i4.0
0xee583  ldloc.s  7
0xee585  stelem.ref
0xee586  ldloc.s  6
0xee588  brfalse.s loc_EE58E
0xee58a  ldc.i4.s 0x40
0xee58c  br.s     loc_EE590
0xee58e  ldc.i4.s 0x12
0xee590  callvirt instance void [System]System.ComponentModel.Design.ISelectionService::SetSelectedComponents(class [mscorlib]System.Collections.ICollection, valuetype [System]System.ComponentModel.Design.SelectionTypes)
0xee595  ldloc.s  6
0xee597  ldc.i4.1
0xee598  add
0xee599  stloc.s  6
0xee59b  ldloc.s  6
0xee59d  ldarg.1
0xee59e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xee5a3  blt      loc_EE46D
0xee5a8  leave.s  loc_EE5C4
0xee5aa  pop
0xee5ab  ldloc.2
0xee5ac  brfalse.s loc_EE5B6
0xee5ae  ldloc.2
0xee5af  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Cancel()
0xee5b4  ldnull
0xee5b5  stloc.2
0xee5b6  leave.s  loc_EE5C4
0xee5b8  ldloc.2
0xee5b9  brfalse.s loc_EE5C3
0xee5bb  ldloc.2
0xee5bc  callvirt instance void [System]System.ComponentModel.Design.DesignerTransaction::Commit()
0xee5c1  ldnull
0xee5c2  stloc.2
0xee5c3  endfinally
0xee5c4  ret
```
