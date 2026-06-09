# System.Windows.Xps.XpsDocumentWriter::SetCompletionEventHandler

- ea: `0xc450`
- end: `0xc4e9`
- name: `System.Windows.Xps.XpsDocumentWriter::SetCompletionEventHandler`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xc6e0`
- `0xd330`

## callees

- `0xc450`

## pseudocode

```c

```

## disassembly

```asm
0xc450  ldarg.2
0xc451  brfalse.s loc_C45A
0xc453  ldarg.0
0xc454  ldarg.2
0xc455  stfld    object System.Windows.Xps.XpsDocumentWriter::_currentUserState
0xc45a  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xc45f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc464  ldarg.1
0xc465  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc46a  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc46f  brfalse.s loc_C48A
0xc471  ldarg.1
0xc472  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xc477  ldarg.0
0xc478  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardWriteCompletedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventArgs args)
0xc47e  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventHandler::.ctor(object, native int)
0xc483  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync::add_XpsSerializationCompleted(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventHandler)
0xc488  br.s     loc_C4E8
0xc48a  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xc48f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc494  ldarg.1
0xc495  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc49a  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc49f  brfalse.s loc_C4BA
0xc4a1  ldarg.1
0xc4a2  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xc4a7  ldarg.0
0xc4a8  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardWriteCompletedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventArgs args)
0xc4ae  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventHandler::.ctor(object, native int)
0xc4b3  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync::add_XpsSerializationCompleted(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventHandler)
0xc4b8  br.s     loc_C4E8
0xc4ba  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xc4bf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc4c4  ldarg.1
0xc4c5  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc4ca  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc4cf  brfalse.s loc_C4E8
0xc4d1  ldarg.1
0xc4d2  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xc4d7  ldarg.0
0xc4d8  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardWriteCompletedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventArgs args)
0xc4de  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventHandler::.ctor(object, native int)
0xc4e3  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync::add_XpsSerializationCompleted(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationCompletedEventHandler)
0xc4e8  ret
```
