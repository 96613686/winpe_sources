# System.Windows.Xps.XpsDocumentWriter::SetPrintTicketEventHandler

- ea: `0xc360`
- end: `0xc443`
- name: `System.Windows.Xps.XpsDocumentWriter::SetPrintTicketEventHandler`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0xc6e0`

## callees

- `0xc360`

## pseudocode

```c

```

## disassembly

```asm
0xc360  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager
0xc365  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc36a  ldarg.1
0xc36b  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc370  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc375  brfalse.s loc_C388
0xc377  ldarg.1
0xc378  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager
0xc37d  ldarg.2
0xc37e  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager::add_XpsSerializationPrintTicketRequired(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler)
0xc383  br       loc_C442
0xc388  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager
0xc38d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc392  ldarg.1
0xc393  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc398  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc39d  brfalse.s loc_C3B0
0xc39f  ldarg.1
0xc3a0  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager
0xc3a5  ldarg.2
0xc3a6  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::add_XpsSerializationPrintTicketRequired(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler)
0xc3ab  br       loc_C442
0xc3b0  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xc3b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc3ba  ldarg.1
0xc3bb  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc3c0  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc3c5  brfalse.s loc_C3D5
0xc3c7  ldarg.1
0xc3c8  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManagerAsync
0xc3cd  ldarg.2
0xc3ce  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsOMSerializationManager::add_XpsSerializationPrintTicketRequired(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler)
0xc3d3  br.s     loc_C442
0xc3d5  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xc3da  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc3df  ldarg.1
0xc3e0  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc3e5  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc3ea  brfalse.s loc_C3FA
0xc3ec  ldarg.1
0xc3ed  castclass [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManagerAsync
0xc3f2  ldarg.2
0xc3f3  call     instance void [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationManager::add_XpsSerializationPrintTicketRequired(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler)
0xc3f8  br.s     loc_C442
0xc3fa  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager
0xc3ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc404  ldarg.1
0xc405  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc40a  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc40f  brfalse.s loc_C41F
0xc411  ldarg.1
0xc412  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager
0xc417  ldarg.2
0xc418  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManager::add_XpsSerializationPrintTicketRequired(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler)
0xc41d  br.s     loc_C442
0xc41f  ldtoken  [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xc424  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc429  ldarg.1
0xc42a  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xc42f  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0xc434  brfalse.s loc_C442
0xc436  ldarg.1
0xc437  castclass [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync
0xc43c  ldarg.2
0xc43d  call     instance void [ReachFramework]System.Windows.Xps.Serialization.NgcSerializationManagerAsync::add_XpsSerializationPrintTicketRequired(class [ReachFramework]System.Windows.Xps.Serialization.XpsSerializationPrintTicketRequiredEventHandler)
0xc442  ret
```
