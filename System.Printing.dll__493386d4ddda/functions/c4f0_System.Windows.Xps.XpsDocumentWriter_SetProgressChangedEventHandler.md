# System.Windows.Xps.XpsDocumentWriter::SetProgressChangedEventHandler

- ea: `0xc4f0`
- end: `0xc622`
- name: `System.Windows.Xps.XpsDocumentWriter::SetProgressChangedEventHandler`
- size: `306`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0xc6e0`
- `0xd330`

## callees

- `0xc4f0`

## pseudocode

```c

```

## disassembly

```asm
0xc4f0  ldarg.2
0xc4f1  brfalse.s loc_C4FA
0xc4f3  ldarg.0
0xc4f4  ldarg.2
0xc4f5  stfld    object System.Windows.Xps.XpsDocumentWriter::_currentUserState
0xc4fa  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager
0xc4ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc504  ldarg.1
0xc505  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc50a  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc50f  brfalse.s loc_C52D
0xc511  ldarg.1
0xc512  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager
0xc517  ldarg.0
0xc518  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardProgressChangedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs args)
0xc51e  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler::.ctor(object, native int)
0xc523  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager::add_XpsSerializationProgressChanged(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler)
0xc528  br       loc_C621
0xc52d  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager
0xc532  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc537  ldarg.1
0xc538  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc53d  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc542  brfalse.s loc_C560
0xc544  ldarg.1
0xc545  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager
0xc54a  ldarg.0
0xc54b  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardProgressChangedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs args)
0xc551  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler::.ctor(object, native int)
0xc556  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::add_XpsSerializationProgressChanged(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler)
0xc55b  br       loc_C621
0xc560  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xc565  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc56a  ldarg.1
0xc56b  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc570  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc575  brfalse.s loc_C593
0xc577  ldarg.1
0xc578  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xc57d  ldarg.0
0xc57e  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardProgressChangedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs args)
0xc584  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler::.ctor(object, native int)
0xc589  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager::add_XpsSerializationProgressChanged(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler)
0xc58e  br       loc_C621
0xc593  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xc598  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc59d  ldarg.1
0xc59e  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc5a3  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc5a8  brfalse.s loc_C5C3
0xc5aa  ldarg.1
0xc5ab  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xc5b0  ldarg.0
0xc5b1  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardProgressChangedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs args)
0xc5b7  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler::.ctor(object, native int)
0xc5bc  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::add_XpsSerializationProgressChanged(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler)
0xc5c1  br.s     loc_C621
0xc5c3  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager
0xc5c8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc5cd  ldarg.1
0xc5ce  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc5d3  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc5d8  brfalse.s loc_C5F3
0xc5da  ldarg.1
0xc5db  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager
0xc5e0  ldarg.0
0xc5e1  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardProgressChangedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs args)
0xc5e7  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler::.ctor(object, native int)
0xc5ec  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager::add_XpsSerializationProgressChanged(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler)
0xc5f1  br.s     loc_C621
0xc5f3  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xc5f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc5fd  ldarg.1
0xc5fe  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc603  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc608  brfalse.s loc_C621
0xc60a  ldarg.1
0xc60b  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xc610  ldarg.0
0xc611  ldftn    instance void System.Windows.Xps.XpsDocumentWriter::ForwardProgressChangedEvent(object sender, class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventArgs args)
0xc617  newobj   instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler::.ctor(object, native int)
0xc61c  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync::add_XpsSerializationProgressChanged(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationProgressChangedEventHandler)
0xc621  ret
```
