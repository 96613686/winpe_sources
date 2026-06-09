# System.Windows.Xps.Serialization.SerializableObjectContext::CreateContext

- ea: `0x33f70`
- end: `0x3406e`
- name: `System.Windows.Xps.Serialization.SerializableObjectContext::CreateContext`
- size: `254`
- prototype: ``
- caller_count: `6`
- callee_count: `15`
- tags: ``

## callers

- `0x2bb70`
- `0x2be70`
- `0x33040`
- `0x33410`
- `0x33530`
- `0x337c0`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x30650`
- `0x33eb0`
- `0x33f60`
- `0x33f70`
- `0x340a0`
- `0x340b0`
- `0x340c0`
- `0x340d0`
- `0x340e0`
- `0x34130`
- `0x35b90`
- `0x35c10`
- `0x35d60`

## pseudocode

```c

```

## disassembly

```asm
0x33f70  ldc.i4.0
0x33f71  stloc.0
0x33f72  ldnull
0x33f73  stloc.1
0x33f74  ldarg.0
0x33f75  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack System.Windows.Xps.Serialization.PackageSerializationManager::get_GraphContextStack()
0x33f7a  ldloc.0
0x33f7b  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(int32)
0x33f80  stloc.1
0x33f81  br.s     loc_33FB7
0x33f83  ldloc.1
0x33f84  isinst   System.Windows.Xps.Serialization.SerializableObjectContext
0x33f89  stloc.3
0x33f8a  ldloc.3
0x33f8b  brfalse.s loc_33FA6
0x33f8d  ldloc.3
0x33f8e  callvirt instance object System.Windows.Xps.Serialization.SerializableObjectContext::get_TargetObject()
0x33f93  ldarg.1
0x33f94  bne.un.s loc_33FA6
0x33f96  ldstr    aReachserializa_18// "ReachSerialization_CycleDetectedInSeria"...
0x33f9b  call     string System.Windows.Xps.SR::Get(string id)
0x33fa0  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x33fa5  throw
0x33fa6  ldarg.0
0x33fa7  callvirt instance class [System]System.ComponentModel.Design.Serialization.ContextStack System.Windows.Xps.Serialization.PackageSerializationManager::get_GraphContextStack()
0x33fac  ldloc.0
0x33fad  ldc.i4.1
0x33fae  add
0x33faf  dup
0x33fb0  stloc.0
0x33fb1  callvirt instance object [System]System.ComponentModel.Design.Serialization.ContextStack::get_Item(int32)
0x33fb6  stloc.1
0x33fb7  ldloc.1
0x33fb8  brtrue.s loc_33F83
0x33fba  ldsfld   object System.Windows.Xps.Serialization.SerializableObjectContext::_stackLock
0x33fbf  stloc.s  4
0x33fc1  ldc.i4.0
0x33fc2  stloc.s  5
0x33fc4  ldloc.s  4
0x33fc6  ldloca.s 5
0x33fc8  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x33fcd  ldsfld   class [mscorlib]System.Collections.Stack System.Windows.Xps.Serialization.SerializableObjectContext::_recycableSerializableObjectContexts
0x33fd2  callvirt instance int32 [mscorlib]System.Collections.Stack::get_Count()
0x33fd7  brfalse.s loc_33FEA
0x33fd9  ldsfld   class [mscorlib]System.Collections.Stack System.Windows.Xps.Serialization.SerializableObjectContext::_recycableSerializableObjectContexts
0x33fde  callvirt instance object [mscorlib]System.Collections.Stack::Pop()
0x33fe3  castclass System.Windows.Xps.Serialization.SerializableObjectContext
0x33fe8  br.s     loc_33FEB
0x33fea  ldnull
0x33feb  stloc.2
0x33fec  leave.s  loc_33FFA
0x33fee  ldloc.s  5
0x33ff0  brfalse.s loc_33FF9
0x33ff2  ldloc.s  4
0x33ff4  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x33ff9  endfinally
0x33ffa  ldloc.2
0x33ffb  brtrue.s loc_34007
0x33ffd  ldarg.1
0x33ffe  ldarg.3
0x33fff  newobj   instance void System.Windows.Xps.Serialization.SerializableObjectContext::.ctor(object target, class System.Windows.Xps.Serialization.SerializablePropertyContext serializablePropertyContext)
0x34004  stloc.2
0x34005  br.s     loc_3400F
0x34007  ldloc.2
0x34008  ldarg.1
0x34009  ldarg.3
0x3400a  callvirt instance void System.Windows.Xps.Serialization.SerializableObjectContext::Initialize(object target, class System.Windows.Xps.Serialization.SerializablePropertyContext serializablePropertyContext)
0x3400f  ldarg.2
0x34010  brtrue.s loc_34015
0x34012  ldnull
0x34013  br.s     loc_3401B
0x34015  ldarg.2
0x34016  callvirt instance class System.Windows.Xps.Serialization.MetroSerializationNamespaceTable System.Windows.Xps.Serialization.SerializableObjectContext::get_NamespaceTable()
0x3401b  stloc.s  6
0x3401d  ldloc.2
0x3401e  callvirt instance class System.Windows.Xps.Serialization.MetroSerializationNamespaceTable System.Windows.Xps.Serialization.SerializableObjectContext::get_NamespaceTable()
0x34023  brtrue.s loc_34032
0x34025  ldloc.2
0x34026  ldloc.s  6
0x34028  newobj   instance void System.Windows.Xps.Serialization.MetroSerializationNamespaceTable::.ctor(class System.Windows.Xps.Serialization.MetroSerializationNamespaceTable parent)
0x3402d  callvirt instance void System.Windows.Xps.Serialization.SerializableObjectContext::set_NamespaceTable(class System.Windows.Xps.Serialization.MetroSerializationNamespaceTable value)
0x34032  ldloc.2
0x34033  callvirt instance class System.Windows.Xps.Serialization.SerializablePropertyCollection System.Windows.Xps.Serialization.SerializableObjectContext::get_PropertiesCollection()
0x34038  brtrue.s loc_34049
0x3403a  ldloc.2
0x3403b  ldarg.0
0x3403c  ldarg.1
0x3403d  newobj   instance void System.Windows.Xps.Serialization.SerializablePropertyCollection::.ctor(class System.Windows.Xps.Serialization.PackageSerializationManager manager, object targetObject)
0x34042  callvirt instance void System.Windows.Xps.Serialization.SerializableObjectContext::set_PropertiesCollection(class System.Windows.Xps.Serialization.SerializablePropertyCollection value)
0x34047  br.s     loc_34056
0x34049  ldloc.2
0x3404a  callvirt instance class System.Windows.Xps.Serialization.SerializablePropertyCollection System.Windows.Xps.Serialization.SerializableObjectContext::get_PropertiesCollection()
0x3404f  ldarg.0
0x34050  ldarg.1
0x34051  callvirt instance void System.Windows.Xps.Serialization.SerializablePropertyCollection::Initialize(class System.Windows.Xps.Serialization.PackageSerializationManager serializationManager, object targetObject)
0x34056  ldloc.2
0x34057  ldloc.2
0x34058  callvirt instance object System.Windows.Xps.Serialization.SerializableObjectContext::get_TargetObject()
0x3405d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x34062  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x34067  callvirt instance void System.Windows.Xps.Serialization.BasicContext::set_Name(string value)
0x3406c  ldloc.2
0x3406d  ret
```
