# System.Windows.Forms.Design.Behavior.DropSourceBehavior::EndDragDrop

- ea: `0xe85f0`
- end: `0xe8d4b`
- name: `System.Windows.Forms.Design.Behavior.DropSourceBehavior::EndDragDrop`
- size: `1883`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x126950`

## callees

- `0x8eec0`
- `0x9d9a0`
- `0xb2d20`
- `0xc97e0`
- `0xe4a90`
- `0xe8080`
- `0xe8480`
- `0xe8540`
- `0xe85f0`
- `0xe9b70`
- `0x126910`
- `0x126930`

## string_xrefs

- `0xe87ba`: `BehaviorServiceMoveControl`
- `0xe87c1`: `BehaviorServiceCopyControl`
- `0xe87dd`: `BehaviorServiceMoveControls`
- `0xe87e4`: `BehaviorServiceCopyControls`

## pseudocode

```c

```

## disassembly

```asm
0xe85f0  ldarg.0
0xe85f1  ldfld    class BehaviorDataObject System.Windows.Forms.Design.Behavior.DropSourceBehavior::data
0xe85f6  callvirt instance class [System]System.ComponentModel.IComponent BehaviorDataObject::get_Target()
0xe85fb  isinst   [System.Windows.Forms]System.Windows.Forms.Control
0xe8600  stloc.0
0xe8601  ldloc.0
0xe8602  brtrue.s loc_E8605
0xe8604  ret
0xe8605  ldarg.0
0xe8606  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe860b  brtrue.s loc_E8622
0xe860d  ldarg.0
0xe860e  ldloc.0
0xe860f  callvirt instance class [System]System.ComponentModel.ISite [System]System.ComponentModel.Component::get_Site()
0xe8614  stfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe8619  ldarg.0
0xe861a  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe861f  brtrue.s loc_E8622
0xe8621  ret
0xe8622  ldarg.0
0xe8623  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe8628  brtrue.s loc_E8653
0xe862a  ldarg.0
0xe862b  ldarg.0
0xe862c  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe8631  ldtoken  [System]System.ComponentModel.Design.IDesignerHost
0xe8636  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe863b  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xe8640  castclass [System]System.ComponentModel.Design.IDesignerHost
0xe8645  stfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe864a  ldarg.0
0xe864b  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe8650  brtrue.s loc_E8653
0xe8652  ret
0xe8653  ldarg.0
0xe8654  ldfld    class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.Behavior.DropSourceBehavior::behaviorServiceTarget
0xe8659  brtrue.s loc_E8684
0xe865b  ldarg.0
0xe865c  ldarg.0
0xe865d  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe8662  ldtoken  System.Windows.Forms.Design.Behavior.BehaviorService
0xe8667  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe866c  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xe8671  castclass System.Windows.Forms.Design.Behavior.BehaviorService
0xe8676  stfld    class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.Behavior.DropSourceBehavior::behaviorServiceTarget
0xe867b  ldarg.0
0xe867c  ldfld    class System.Windows.Forms.Design.Behavior.BehaviorService System.Windows.Forms.Design.Behavior.DropSourceBehavior::behaviorServiceTarget
0xe8681  brtrue.s loc_E8684
0xe8683  ret
0xe8684  ldnull
0xe8685  stloc.1
0xe8686  ldarg.0
0xe8687  ldfld    valuetype [System.Windows.Forms]System.Windows.Forms.DragDropEffects System.Windows.Forms.Design.Behavior.DropSourceBehavior::lastEffect
0xe868c  ldc.i4.1
0xe868d  ceq
0xe868f  stloc.2
0xe8690  ldarg.0
0xe8691  ldfld    class BehaviorDataObject System.Windows.Forms.Design.Behavior.DropSourceBehavior::data
0xe8696  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control BehaviorDataObject::get_Source()
0xe869b  stloc.3
0xe869c  ldloc.3
0xe869d  ldloc.0
0xe869e  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xe86a3  stloc.s  4
0xe86a5  ldloc.0
0xe86a6  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xe86ab  ldstr    aControls// "Controls"
0xe86b0  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xe86b5  stloc.s  5
0xe86b7  ldloc.3
0xe86b8  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0xe86bd  ldstr    aControls// "Controls"
0xe86c2  callvirt instance class [System]System.ComponentModel.PropertyDescriptor [System]System.ComponentModel.PropertyDescriptorCollection::get_Item(string)
0xe86c7  stloc.s  6
0xe86c9  ldarg.0
0xe86ca  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderSource
0xe86cf  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0xe86d4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe86d9  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xe86de  castclass [System]System.ComponentModel.Design.IComponentChangeService
0xe86e3  stloc.s  7
0xe86e5  ldarg.0
0xe86e6  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe86eb  ldtoken  [System]System.ComponentModel.Design.IComponentChangeService
0xe86f0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe86f5  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xe86fa  castclass [System]System.ComponentModel.Design.IComponentChangeService
0xe86ff  stloc.s  8
0xe8701  ldarg.0
0xe8702  ldfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragAssistanceManager
0xe8707  brfalse.s loc_E8714
0xe8709  ldarg.0
0xe870a  ldfld    class System.Windows.Forms.Design.Behavior.DragAssistanceManager System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragAssistanceManager
0xe870f  callvirt instance void System.Windows.Forms.Design.Behavior.DragAssistanceManager::OnMouseUp()
0xe8714  ldnull
0xe8715  stloc.s  9
0xe8717  ldloc.2
0xe8718  brtrue.s loc_E8730
0xe871a  ldarg.0
0xe871b  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::srcHost
0xe8720  ldarg.0
0xe8721  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe8726  beq.s    loc_E874C
0xe8728  ldarg.0
0xe8729  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe872e  brfalse.s loc_E874C
0xe8730  ldarg.0
0xe8731  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe8736  ldtoken  [System]System.ComponentModel.Design.ISelectionService
0xe873b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe8740  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xe8745  castclass [System]System.ComponentModel.Design.ISelectionService
0xe874a  stloc.s  9
0xe874c  nop
0xe874d  ldarg.0
0xe874e  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe8753  brfalse  loc_E8CC1
0xe8758  ldarg.0
0xe8759  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe875e  ldlen
0xe875f  brfalse  loc_E8CC1
0xe8764  ldnull
0xe8765  stloc.s  0xA
0xe8767  ldnull
0xe8768  stloc.s  0xB
0xe876a  ldarg.0
0xe876b  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe8770  ldlen
0xe8771  conv.i4
0xe8772  ldc.i4.1
0xe8773  bne.un.s loc_E87DA
0xe8775  ldarg.0
0xe8776  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe877b  ldc.i4.0
0xe877c  ldelema  DragComponent
0xe8781  ldfld    object DragComponent::dragComponent
0xe8786  call     string [System]System.ComponentModel.TypeDescriptor::GetComponentName(object)
0xe878b  stloc.s  0xD
0xe878d  ldloc.s  0xD
0xe878f  brfalse.s loc_E879A
0xe8791  ldloc.s  0xD
0xe8793  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe8798  brtrue.s loc_E87B7
0xe879a  ldarg.0
0xe879b  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe87a0  ldc.i4.0
0xe87a1  ldelema  DragComponent
0xe87a6  ldfld    object DragComponent::dragComponent
0xe87ab  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xe87b0  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xe87b5  stloc.s  0xD
0xe87b7  ldloc.2
0xe87b8  brtrue.s loc_E87C1
0xe87ba  ldstr    aBehaviorservic// "BehaviorServiceMoveControl"
0xe87bf  br.s     loc_E87C6
0xe87c1  ldstr    aBehaviorservic_0// "BehaviorServiceCopyControl"
0xe87c6  ldc.i4.1
0xe87c7  newarr   [mscorlib]System.Object
0xe87cc  dup
0xe87cd  ldc.i4.0
0xe87ce  ldloc.s  0xD
0xe87d0  stelem.ref
0xe87d1  call     string System.Design.SR::GetString(string name, object[] args)
0xe87d6  stloc.s  0xC
0xe87d8  br.s     loc_E8806
0xe87da  ldloc.2
0xe87db  brtrue.s loc_E87E4
0xe87dd  ldstr    aBehaviorservic_1// "BehaviorServiceMoveControls"
0xe87e2  br.s     loc_E87E9
0xe87e4  ldstr    aBehaviorservic_2// "BehaviorServiceCopyControls"
0xe87e9  ldc.i4.1
0xe87ea  newarr   [mscorlib]System.Object
0xe87ef  dup
0xe87f0  ldc.i4.0
0xe87f1  ldarg.0
0xe87f2  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe87f7  ldlen
0xe87f8  conv.i4
0xe87f9  box      [mscorlib]System.Int32
0xe87fe  stelem.ref
0xe87ff  call     string System.Design.SR::GetString(string name, object[] args)
0xe8804  stloc.s  0xC
0xe8806  ldarg.0
0xe8807  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::srcHost
0xe880c  brfalse.s loc_E883B
0xe880e  ldarg.0
0xe880f  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::srcHost
0xe8814  ldarg.0
0xe8815  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe881a  beq.s    loc_E8827
0xe881c  ldarg.0
0xe881d  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe8822  ldnull
0xe8823  cgt.un
0xe8825  br.s     loc_E8828
0xe8827  ldc.i4.0
0xe8828  ldloc.2
0xe8829  and
0xe882a  brtrue.s loc_E883B
0xe882c  ldarg.0
0xe882d  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::srcHost
0xe8832  ldloc.s  0xC
0xe8834  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xe8839  stloc.s  0xA
0xe883b  ldarg.0
0xe883c  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::srcHost
0xe8841  ldarg.0
0xe8842  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe8847  beq.s    loc_E8860
0xe8849  ldarg.0
0xe884a  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe884f  brfalse.s loc_E8860
0xe8851  ldarg.0
0xe8852  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.Windows.Forms.Design.Behavior.DropSourceBehavior::destHost
0xe8857  ldloc.s  0xC
0xe8859  callvirt instance class [System]System.ComponentModel.Design.DesignerTransaction [System]System.ComponentModel.Design.IDesignerHost::CreateTransaction(string)
0xe885e  stloc.s  0xB
0xe8860  nop
0xe8861  ldnull
0xe8862  stloc.s  0xE
0xe8864  ldc.i4.0
0xe8865  stloc.s  0xF
0xe8867  ldloc.2
0xe8868  brfalse  loc_E8943
0xe886d  ldarg.0
0xe886e  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe8873  ldtoken  System.Windows.Forms.Design.ComponentTray
0xe8878  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe887d  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0xe8882  isinst   System.Windows.Forms.Design.ComponentTray
0xe8887  stloc.s  0xE
0xe8889  ldloc.s  0xE
0xe888b  brtrue.s loc_E8890
0xe888d  ldc.i4.0
0xe888e  br.s     loc_E889C
0xe8890  ldloc.s  0xE
0xe8892  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xe8897  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Layout.ArrangedElementCollection::get_Count()
0xe889c  stloc.s  0xF
0xe889e  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xe88a3  stloc.s  0x13
0xe88a5  ldc.i4.0
0xe88a6  stloc.s  0x14
0xe88a8  br.s     loc_E88CA
0xe88aa  ldloc.s  0x13
0xe88ac  ldarg.0
0xe88ad  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe88b2  ldloc.s  0x14
0xe88b4  ldelema  DragComponent
0xe88b9  ldfld    object DragComponent::dragComponent
0xe88be  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xe88c3  pop
0xe88c4  ldloc.s  0x14
0xe88c6  ldc.i4.1
0xe88c7  add
0xe88c8  stloc.s  0x14
0xe88ca  ldloc.s  0x14
0xe88cc  ldarg.0
0xe88cd  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe88d2  ldlen
0xe88d3  conv.i4
0xe88d4  blt.s    loc_E88AA
0xe88d6  ldloc.s  0x13
0xe88d8  ldarg.0
0xe88d9  ldfld    class [mscorlib]System.IServiceProvider System.Windows.Forms.Design.Behavior.DropSourceBehavior::serviceProviderTarget
0xe88de  call     class [mscorlib]System.Collections.ICollection System.Windows.Forms.Design.DesignerUtils::CopyDragObjects(class [mscorlib]System.Collections.ICollection objects, class [mscorlib]System.IServiceProvider svcProvider)
0xe88e3  isinst   [mscorlib]System.Collections.ArrayList
0xe88e8  stloc.s  0x13
0xe88ea  ldloc.s  0x13
0xe88ec  brtrue.s loc_E88F3
0xe88ee  leave    loc_E8D4A
0xe88f3  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xe88f8  stloc.1
0xe88f9  ldc.i4.0
0xe88fa  stloc.s  0x15
0xe88fc  br.s     loc_E8938
0xe88fe  ldloc.1
0xe88ff  ldarg.0
0xe8900  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe8905  ldloc.s  0x15
0xe8907  ldelema  DragComponent
0xe890c  ldfld    object DragComponent::dragComponent
0xe8911  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xe8916  pop
0xe8917  ldarg.0
0xe8918  ldfld    valuetype DragComponent[] System.Windows.Forms.Design.Behavior.DropSourceBehavior::dragComponents
0xe891d  ldloc.s  0x15
0xe891f  ldelema  DragComponent
0xe8924  ldloc.s  0x13
0xe8926  ldloc.s  0x15
0xe8928  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xe892d  stfld    object DragComponent::dragComponent
0xe8932  ldloc.s  0x15
0xe8934  ldc.i4.1
0xe8935  add
0xe8936  stloc.s  0x15
0xe8938  ldloc.s  0x15
0xe893a  ldloc.s  0x13
0xe893c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xe8941  blt.s    loc_E88FE
  ... truncated ...
```
