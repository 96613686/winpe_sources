# System.Windows.Forms.Design.CommandSet::OnKeyMove

- ea: `0x991a0`
- end: `0x995f7`
- name: `System.Windows.Forms.Design.CommandSet::OnKeyMove`
- size: `1111`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0xa1740`

## callees

- `0x8eec0`
- `0x98a50`
- `0x98ab0`
- `0x98ad0`
- `0x98d00`
- `0x98f50`
- `0x98fa0`
- `0x991a0`
- `0xa29d0`
- `0xc27e0`
- `0xc97e0`
- `0xe4a60`
- `0xe6930`
- `0xe7460`
- `0xe8010`

## string_xrefs

- `0x992dc`: `DragDropMoveComponents`
- `0x99304`: `DragDropMoveComponent`

## pseudocode

```c

```

## disassembly

```asm
0x991a0  ldarg.0
0x991a1  call     instance class [System]System.ComponentModel.Design.ISelectionService System.Windows.Forms.Design.CommandSet::get_SelectionService()
0x991a6  stloc.0
0x991a7  ldloc.0
0x991a8  brfalse  loc_995F6
0x991ad  ldloc.0
0x991ae  callvirt instance object [System]System.ComponentModel.Design.ISelectionService::get_PrimarySelection()
0x991b3  isinst   [System]System.ComponentModel.IComponent
0x991b8  stloc.1
0x991b9  ldloc.1
0x991ba  brfalse  loc_995F6
0x991bf  ldarg.0
0x991c0  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0x991c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x991ca  callvirt instance object System.Windows.Forms.Design.CommandSet::GetService(class [mscorlib]System.Type serviceType)
0x991cf  castclass [System]System.ComponentModel.Design.IDesignerHost
0x991d4  stloc.2
0x991d5  ldloc.2
0x991d6  brfalse  loc_995F6
0x991db  ldloc.1
0x991dc  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x991e1  ldstr    aLocked// "Locked"
0x991e6  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0x991eb  stloc.3
0x991ec  ldloc.3
0x991ed  brfalse.s loc_99217
0x991ef  ldloc.3
0x991f0  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.PropertyDescriptor::get_PropertyType()
0x991f5  ldtoken  [mscorlib]System.Boolean
0x991fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x991ff  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x99204  brfalse.s loc_99217
0x99206  ldloc.3
0x99207  ldloc.1
0x99208  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x9920d  unbox.any [mscorlib]System.Boolean
0x99212  brtrue   loc_995F6
0x99217  ldarg.1
0x99218  castclass [System]System.ComponentModel.Design.MenuCommand
0x9921d  callvirt instance class [System]System.ComponentModel.Design.CommandID [System]System.ComponentModel.Design.MenuCommand::get_CommandID()
0x99222  stloc.s  4
0x99224  ldc.i4.0
0x99225  stloc.s  5
0x99227  ldc.i4.0
0x99228  stloc.s  6
0x9922a  ldc.i4.0
0x9922b  stloc.s  7
0x9922d  ldloc.s  4
0x9922f  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyMoveUp
0x99234  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x99239  brfalse.s loc_99243
0x9923b  ldc.i4.m1
0x9923c  stloc.s  7
0x9923e  br       loc_992D2
0x99243  ldloc.s  4
0x99245  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyMoveDown
0x9924a  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x9924f  brfalse.s loc_99256
0x99251  ldc.i4.1
0x99252  stloc.s  7
0x99254  br.s     loc_992D2
0x99256  ldloc.s  4
0x99258  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyMoveLeft
0x9925d  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x99262  brfalse.s loc_99269
0x99264  ldc.i4.m1
0x99265  stloc.s  6
0x99267  br.s     loc_992D2
0x99269  ldloc.s  4
0x9926b  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyMoveRight
0x99270  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x99275  brfalse.s loc_9927C
0x99277  ldc.i4.1
0x99278  stloc.s  6
0x9927a  br.s     loc_992D2
0x9927c  ldloc.s  4
0x9927e  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyNudgeUp
0x99283  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x99288  brfalse.s loc_99292
0x9928a  ldc.i4.m1
0x9928b  stloc.s  7
0x9928d  ldc.i4.1
0x9928e  stloc.s  5
0x99290  br.s     loc_992D2
0x99292  ldloc.s  4
0x99294  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyNudgeDown
0x99299  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x9929e  brfalse.s loc_992A8
0x992a0  ldc.i4.1
0x992a1  stloc.s  7
0x992a3  ldc.i4.1
0x992a4  stloc.s  5
0x992a6  br.s     loc_992D2
0x992a8  ldloc.s  4
0x992aa  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyNudgeLeft
0x992af  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x992b4  brfalse.s loc_992BE
0x992b6  ldc.i4.m1
0x992b7  stloc.s  6
0x992b9  ldc.i4.1
0x992ba  stloc.s  5
0x992bc  br.s     loc_992D2
0x992be  ldloc.s  4
0x992c0  ldsfld   class [System]System.ComponentModel.Design.CommandID System.Windows.Forms.Design.MenuCommands::KeyNudgeRight
0x992c5  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x992ca  brfalse.s loc_992D2
0x992cc  ldc.i4.1
0x992cd  stloc.s  6
0x992cf  ldc.i4.1
0x992d0  stloc.s  5
0x992d2  ldloc.0
0x992d3  callvirt instance int32 [System]System.ComponentModel.Design.ISelectionService::get_SelectionCount()
0x992d8  ldc.i4.1
0x992d9  ble.s    loc_99303
0x992db  ldloc.2
0x992dc  ldstr    aDragdropmoveco// "DragDropMoveComponents"
0x992e1  ldc.i4.1
0x992e2  newarr   [mscorlib]System.Object
0x992e7  dup
0x992e8  ldc.i4.0
0x992e9  ldloc.0
0x992ea  callvirt instance int32 [System]System.ComponentModel.Design.ISelectionService::get_SelectionCount()
0x992ef  box      [mscorlib]System.Int32
0x992f4  stelem.ref
0x992f5  call     string System.Design.SR::GetString(string name, object[] args)
0x992fa  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x992ff  stloc.s  8
0x99301  br.s     loc_99329
0x99303  ldloc.2
0x99304  ldstr    aDragdropmoveco_0// "DragDropMoveComponent"
0x99309  ldc.i4.1
0x9930a  newarr   [mscorlib]System.Object
0x9930f  dup
0x99310  ldc.i4.0
0x99311  ldloc.1
0x99312  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x99317  callvirt instance string [System]System.ComponentModel.ISite::get_Name()
0x9931c  stelem.ref
0x9931d  call     string System.Design.SR::GetString(string name, object[] args)
0x99322  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0x99327  stloc.s  8
0x99329  nop
0x9932a  ldarg.0
0x9932b  call     instance class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.CommandSet::get_BehaviorService()
0x99330  brfalse  loc_995CA
0x99335  ldloc.1
0x99336  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0x9933b  stloc.s  9
0x9933d  ldarg.0
0x9933e  call     instance class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.CommandSet::get_BehaviorService()
0x99343  callvirt instance bool System.Windows.Forms.Design.Behavior.BehaviorService::get_UseSnapLines()
0x99348  stloc.s  0xA
0x9934a  ldarg.0
0x9934b  ldfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.CommandSet::dragManager
0x99350  brfalse.s loc_99358
0x99352  ldarg.0
0x99353  call     instance void System.Windows.Forms.Design.CommandSet::EndDragManager()
0x99358  ldloc.s  5
0x9935a  ldloc.s  0xA
0x9935c  and
0x9935d  brfalse.s loc_993C9
0x9935f  ldloc.s  9
0x99361  brfalse.s loc_993C9
0x99363  ldloc.0
0x99364  callvirt instance class [mscorlib]System.Collections.ICollection [System]System.ComponentModel.Design.ISelectionService::GetSelectedComponents()
0x99369  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(class [mscorlib]System.Collections.ICollection)
0x9936e  stloc.s  0xC
0x99370  ldarg.0
0x99371  ldloc.1
0x99372  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.IComponent::get_Site()
0x99377  ldloc.s  0xC
0x99379  newobj   instance void System.Windows.Forms.Design.Behavior.DragAssistanceManager::.ctor(class [mscorlib]System.IServiceProvider serviceProvider, class [mscorlib]System.Collections.ArrayList dragComponents)
0x9937e  stfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.CommandSet::dragManager
0x99383  ldarg.0
0x99384  ldfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.CommandSet::dragManager
0x99389  ldloc.s  9
0x9938b  ldloc.s  6
0x9938d  ldloc.s  7
0x9938f  newobj   instance void [System.Drawing]System.Drawing.Point::.ctor(int32, int32)
0x99394  callvirt instance valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.Behavior.DragAssistanceManager::OffsetToNearestSnapLocation(class [System.Windows.Forms]System.Windows.Forms.Control targetControl, valuetype [System.Drawing]System.Drawing.Point directionOffset)
0x99399  stloc.s  0xD
0x9939b  ldloca.s 0xD
0x9939d  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x993a2  stloc.s  6
0x993a4  ldloca.s 0xD
0x993a6  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x993ab  stloc.s  7
0x993ad  ldloc.s  9
0x993af  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x993b4  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_IsMirrored()
0x993b9  brfalse  loc_994F9
0x993be  ldloc.s  6
0x993c0  ldc.i4.m1
0x993c1  mul
0x993c2  stloc.s  6
0x993c4  br       loc_994F9
0x993c9  ldloc.s  5
0x993cb  brtrue   loc_994E1
0x993d0  ldloc.s  0xA
0x993d2  brtrue   loc_994E1
0x993d7  ldc.i4.0
0x993d8  stloc.s  0xE
0x993da  ldsfld   valuetype [System.Drawing]System.Drawing.Size [System.Drawing]System.Drawing.Size::Empty
0x993df  stloc.s  0xF
0x993e1  ldnull
0x993e2  stloc.s  0x10
0x993e4  ldnull
0x993e5  stloc.s  0x11
0x993e7  ldarg.0
0x993e8  ldloc.2
0x993e9  ldloc.1
0x993ea  ldloca.s 0xF
0x993ec  ldloca.s 0x10
0x993ee  ldloca.s 0x11
0x993f0  callvirt instance void System.Windows.Forms.Design.CommandSet::GetSnapInformation(class [System]System.ComponentModel.Design.IDesignerHost host, class [System]System.ComponentModel.IComponent component, [out] valuetype [System.Drawing]System.Drawing.Size& snapSize, [out] class [System]System.ComponentModel.IComponent& snapComponent, [out] class [System]System.ComponentModel.PropertyDescriptor& snapProperty)
0x993f5  ldloc.s  0x11
0x993f7  brfalse.s loc_99409
0x993f9  ldloc.s  0x11
0x993fb  ldloc.s  0x10
0x993fd  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x99402  unbox.any [mscorlib]System.Boolean
0x99407  stloc.s  0xE
0x99409  ldloc.s  0xE
0x9940b  brfalse  loc_994C7
0x99410  ldloca.s 0xF
0x99412  call     instance bool [System.Drawing]System.Drawing.Size::get_IsEmpty()
0x99417  brtrue   loc_994C7
0x9941c  ldloc.s  6
0x9941e  ldloca.s 0xF
0x99420  call     instance int32 [System.Drawing]System.Drawing.Size::get_Width()
0x99425  mul
0x99426  stloc.s  6
0x99428  ldloc.s  7
0x9942a  ldloca.s 0xF
0x9942c  call     instance int32 [System.Drawing]System.Drawing.Size::get_Height()
0x99431  mul
0x99432  stloc.s  7
0x99434  ldloc.s  9
0x99436  brfalse  loc_994F9
0x9943b  ldloc.2
0x9943c  ldloc.s  9
0x9943e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x99443  callvirt instance class [System]System.ComponentModel.Design.IDesigner [System]System.ComponentModel.Design.IDesignerHost::GetDesigner(class [System]System.ComponentModel.IComponent)
0x99448  isinst   System.Windows.Forms.Design.ParentControlDesigner
0x9944d  stloc.s  0x12
0x9944f  ldloc.s  0x12
0x99451  brfalse  loc_994F9
0x99456  ldloc.s  9
0x99458  callvirt instance valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_Location()
0x9945d  stloc.s  0x13
0x9945f  ldloc.s  9
0x99461  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x99466  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_IsMirrored()
0x9946b  brfalse.s loc_99473
0x9946d  ldloc.s  6
0x9946f  ldc.i4.m1
0x99470  mul
0x99471  stloc.s  6
0x99473  ldloca.s 0x13
0x99475  ldloc.s  6
0x99477  ldloc.s  7
0x99479  call     instance void [System.Drawing]System.Drawing.Point::Offset(int32, int32)
0x9947e  ldloc.s  0x12
0x99480  ldloc.s  0x13
0x99482  callvirt instance valuetype [System.Drawing]System.Drawing.Point System.Windows.Forms.Design.ParentControlDesigner::GetSnappedPoint(valuetype [System.Drawing]System.Drawing.Point pt)
0x99487  stloc.s  0x13
0x99489  ldloc.s  6
0x9948b  brfalse.s loc_994A7
0x9948d  ldloca.s 0x13
0x9948f  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x99494  ldloc.s  9
0x99496  callvirt instance valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_Location()
0x9949b  stloc.s  0x14
0x9949d  ldloca.s 0x14
0x9949f  call     instance int32 [System.Drawing]System.Drawing.Point::get_X()
0x994a4  sub
0x994a5  stloc.s  6
0x994a7  ldloc.s  7
0x994a9  brfalse.s loc_994F9
0x994ab  ldloca.s 0x13
0x994ad  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x994b2  ldloc.s  9
0x994b4  callvirt instance valuetype [System.Drawing]System.Drawing.Point [System.Windows.Forms]System.Windows.Forms.Control::get_Location()
0x994b9  stloc.s  0x14
0x994bb  ldloca.s 0x14
0x994bd  call     instance int32 [System.Drawing]System.Drawing.Point::get_Y()
0x994c2  sub
0x994c3  stloc.s  7
0x994c5  br.s     loc_994F9
0x994c7  ldloc.s  9
0x994c9  brfalse.s loc_994F9
0x994cb  ldloc.s  9
0x994cd  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control [System.Windows.Forms]System.Windows.Forms.Control::get_Parent()
0x994d2  callvirt instance bool [System.Windows.Forms]System.Windows.Forms.Control::get_IsMirrored()
0x994d7  brfalse.s loc_994F9
0x994d9  ldloc.s  6
0x994db  ldc.i4.m1
0x994dc  mul
0x994dd  stloc.s  6
0x994df  br.s     loc_994F9
  ... truncated ...
```
