# System.ComponentModel.Design.UndoEngine::OnComponentRemoving

- ea: `0x62ee0`
- end: `0x630fc`
- name: `System.ComponentModel.Design.UndoEngine::OnComponentRemoving`
- size: `540`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x629c0`
- `0x62af0`
- `0x62ee0`
- `0x8eec0`
- `0x8ef40`
- `0x10a4f0`
- `0x10aba0`

## string_xrefs

- `0x62f05`: `UndoEngineComponentRemove1`
- `0x62f28`: `UndoEngineComponentRemove0`

## pseudocode

```c

```

## disassembly

```asm
0x62ee0  ldarg.0
0x62ee1  ldfld    bool System.ComponentModel.Design.UndoEngine::_enabled
0x62ee6  brfalse.s loc_62F46
0x62ee8  ldarg.0
0x62ee9  ldfld    class UndoUnit System.ComponentModel.Design.UndoEngine::_executingUnit
0x62eee  brtrue.s loc_62F46
0x62ef0  ldarg.0
0x62ef1  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x62ef6  callvirt instance int32 [mscorlib]System.Collections.Stack::get_Count()
0x62efb  brtrue.s loc_62F46
0x62efd  ldarg.2
0x62efe  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.ComponentEventArgs::get_Component()
0x62f03  brfalse.s loc_62F28
0x62f05  ldstr    aUndoenginecomp_4// "UndoEngineComponentRemove1"
0x62f0a  ldc.i4.1
0x62f0b  newarr   [mscorlib]System.Object
0x62f10  dup
0x62f11  ldc.i4.0
0x62f12  ldarg.0
0x62f13  ldarg.2
0x62f14  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.ComponentEventArgs::get_Component()
0x62f19  ldc.i4.1
0x62f1a  call     instance string System.ComponentModel.Design.UndoEngine::GetName(object obj, bool generateNew)
0x62f1f  stelem.ref
0x62f20  call     string System.Design.SR::GetString(string name, object[] args)
0x62f25  stloc.0
0x62f26  br.s     loc_62F33
0x62f28  ldstr    aUndoenginecomp_5// "UndoEngineComponentRemove0"
0x62f2d  call     string System.Design.SR::GetString(string name)
0x62f32  stloc.0
0x62f33  ldarg.0
0x62f34  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x62f39  ldarg.0
0x62f3a  ldloc.0
0x62f3b  ldc.i4.1
0x62f3c  callvirt instance class UndoUnit System.ComponentModel.Design.UndoEngine::CreateUndoUnit(string name, bool primary)
0x62f41  callvirt instance void [mscorlib]System.Collections.Stack::Push(object)
0x62f46  ldarg.0
0x62f47  ldfld    bool System.ComponentModel.Design.UndoEngine::_enabled
0x62f4c  brfalse  loc_630B6
0x62f51  ldarg.0
0x62f52  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.ComponentModel.Design.UndoEngine::_host
0x62f57  brfalse  loc_630B6
0x62f5c  ldarg.0
0x62f5d  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.ComponentModel.Design.UndoEngine::_host
0x62f62  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.Design.IDesignerHost::get_Container()
0x62f67  brfalse  loc_630B6
0x62f6c  ldarg.0
0x62f6d  ldfld    class [System]System.ComponentModel.Design.IComponentChangeService System.ComponentModel.Design.UndoEngine::_componentChangeService
0x62f72  brfalse  loc_630B6
0x62f77  ldnull
0x62f78  stloc.1
0x62f79  ldarg.0
0x62f7a  ldfld    class [System]System.ComponentModel.Design.IDesignerHost System.ComponentModel.Design.UndoEngine::_host
0x62f7f  callvirt instance class [System]System.ComponentModel.IContainer [System]System.ComponentModel.Design.IDesignerHost::get_Container()
0x62f84  callvirt instance class [System]System.ComponentModel.ComponentCollection [System]System.ComponentModel.IContainer::get_Components()
0x62f89  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ReadOnlyCollectionBase::GetEnumerator()
0x62f8e  stloc.2
0x62f8f  br       loc_63095
0x62f94  ldloc.2
0x62f95  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x62f9a  castclass [System]System.ComponentModel.IComponent
0x62f9f  stloc.3
0x62fa0  ldloc.3
0x62fa1  ldarg.2
0x62fa2  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.ComponentEventArgs::get_Component()
0x62fa7  beq      loc_63095
0x62fac  ldloc.3
0x62fad  call     class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.TypeDescriptor::GetProperties(object)
0x62fb2  stloc.s  4
0x62fb4  ldloc.s  4
0x62fb6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.ComponentModel.PropertyDescriptorCollection::GetEnumerator()
0x62fbb  stloc.s  5
0x62fbd  br       loc_63072
0x62fc2  ldloc.s  5
0x62fc4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x62fc9  castclass [System]System.ComponentModel.PropertyDescriptor
0x62fce  stloc.s  6
0x62fd0  ldloc.s  6
0x62fd2  callvirt instance class [mscorlib]System.Type [System]System.ComponentModel.PropertyDescriptor::get_PropertyType()
0x62fd7  ldarg.2
0x62fd8  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.ComponentEventArgs::get_Component()
0x62fdd  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x62fe2  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x62fe7  brfalse  loc_63072
0x62fec  ldloc.s  6
0x62fee  callvirt instance class [System]System.ComponentModel.AttributeCollection [System]System.ComponentModel.MemberDescriptor::get_Attributes()
0x62ff3  ldsfld   class [System]System.ComponentModel.DesignerSerializationVisibilityAttribute [System]System.ComponentModel.DesignerSerializationVisibilityAttribute::Hidden
0x62ff8  callvirt instance bool [System]System.ComponentModel.AttributeCollection::Contains(class [mscorlib]System.Attribute)
0x62ffd  brtrue.s loc_63072
0x62fff  ldloc.s  6
0x63001  callvirt instance bool [System]System.ComponentModel.PropertyDescriptor::get_IsReadOnly()
0x63006  brtrue.s loc_63072
0x63008  ldnull
0x63009  stloc.s  7
0x6300b  ldloc.s  6
0x6300d  ldloc.3
0x6300e  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x63013  stloc.s  7
0x63015  leave.s  loc_6301A
0x63017  pop
0x63018  leave.s  loc_63072
0x6301a  ldloc.s  7
0x6301c  brfalse.s loc_63072
0x6301e  ldloc.s  7
0x63020  ldarg.2
0x63021  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.ComponentEventArgs::get_Component()
0x63026  bne.un.s loc_63072
0x63028  ldloc.1
0x63029  brtrue.s loc_63056
0x6302b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype ReferencingComponent>::.ctor()
0x63030  stloc.1
0x63031  ldarg.0
0x63032  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.ComponentModel.IComponent, class [mscorlib]System.Collections.Generic.List`1<valuetype ReferencingComponent>> System.ComponentModel.Design.UndoEngine::_refToRemovedComponent
0x63037  brtrue.s loc_63044
0x63039  ldarg.0
0x6303a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.ComponentModel.IComponent, class [mscorlib]System.Collections.Generic.List`1<valuetype ReferencingComponent>>::.ctor()
0x6303f  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.ComponentModel.IComponent, class [mscorlib]System.Collections.Generic.List`1<valuetype ReferencingComponent>> System.ComponentModel.Design.UndoEngine::_refToRemovedComponent
0x63044  ldarg.0
0x63045  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.ComponentModel.IComponent, class [mscorlib]System.Collections.Generic.List`1<valuetype ReferencingComponent>> System.ComponentModel.Design.UndoEngine::_refToRemovedComponent
0x6304a  ldarg.2
0x6304b  callvirt instance class [System]System.ComponentModel.IComponent [System]System.ComponentModel.Design.ComponentEventArgs::get_Component()
0x63050  ldloc.1
0x63051  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.ComponentModel.IComponent, class [mscorlib]System.Collections.Generic.List`1<valuetype ReferencingComponent>>::set_Item(var<u1>, !!T0)
0x63056  ldarg.0
0x63057  ldfld    class [System]System.ComponentModel.Design.IComponentChangeService System.ComponentModel.Design.UndoEngine::_componentChangeService
0x6305c  ldloc.3
0x6305d  ldloc.s  6
0x6305f  callvirt instance void [System]System.ComponentModel.Design.IComponentChangeService::OnComponentChanging(object, class [System]System.ComponentModel.MemberDescriptor)
0x63064  ldloc.1
0x63065  ldloc.3
0x63066  ldloc.s  6
0x63068  newobj   instance void ReferencingComponent::.ctor(class [System]System.ComponentModel.IComponent component, class [System]System.ComponentModel.MemberDescriptor member)
0x6306d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype ReferencingComponent>::Add(var<u1>)
0x63072  ldloc.s  5
0x63074  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x63079  brtrue   loc_62FC2
0x6307e  leave.s  loc_63095
0x63080  ldloc.s  5
0x63082  isinst   [mscorlib]System.IDisposable
0x63087  stloc.s  8
0x63089  ldloc.s  8
0x6308b  brfalse.s loc_63094
0x6308d  ldloc.s  8
0x6308f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63094  endfinally
0x63095  ldloc.2
0x63096  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6309b  brtrue   loc_62F94
0x630a0  leave.s  loc_630B6
0x630a2  ldloc.2
0x630a3  isinst   [mscorlib]System.IDisposable
0x630a8  stloc.s  8
0x630aa  ldloc.s  8
0x630ac  brfalse.s loc_630B5
0x630ae  ldloc.s  8
0x630b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x630b5  endfinally
0x630b6  ldarg.0
0x630b7  ldfld    class [mscorlib]System.Collections.Stack System.ComponentModel.Design.UndoEngine::_unitStack
0x630bc  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.Stack::GetEnumerator()
0x630c1  stloc.s  9
0x630c3  br.s     loc_630DB
0x630c5  ldloc.s  9
0x630c7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x630cc  castclass UndoUnit
0x630d1  stloc.s  0xA
0x630d3  ldloc.s  0xA
0x630d5  ldarg.2
0x630d6  callvirt instance void UndoUnit::ComponentRemoving(class [System]System.ComponentModel.Design.ComponentEventArgs e)
0x630db  ldloc.s  9
0x630dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x630e2  brtrue.s loc_630C5
0x630e4  leave.s  loc_630FB
0x630e6  ldloc.s  9
0x630e8  isinst   [mscorlib]System.IDisposable
0x630ed  stloc.s  8
0x630ef  ldloc.s  8
0x630f1  brfalse.s loc_630FA
0x630f3  ldloc.s  8
0x630f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x630fa  endfinally
0x630fb  ret
```
