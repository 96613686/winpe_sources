# System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureNoCache

- ea: `0x403f0`
- end: `0x40554`
- name: `System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureNoCache`
- size: `356`
- prototype: ``
- caller_count: `8`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x407e0`
- `0x407f0`
- `0x40800`
- `0x40810`
- `0x4bbe0`
- `0x4eb20`
- `0x505b0`
- `0x50670`

## callees

- `0x3f070`
- `0x3f170`
- `0x3fcc0`
- `0x3ff00`
- `0x3ff10`
- `0x3ff40`
- `0x3ffd0`
- `0x3fff0`
- `0x400f0`
- `0x40290`
- `0x402a0`
- `0x40310`
- `0x40320`
- `0x40330`
- `0x403d0`
- `0x403f0`
- `0x405c0`
- `0x40670`
- `0x406e0`

## string_xrefs

- `0x40464`: `$$$cache`

## pseudocode

```c

```

## disassembly

```asm
0x403f0  ldarg.0
0x403f1  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x403f6  call     instance bool System.Xml.Xsl.IlGen.StorageDescriptor::get_IsCached()
0x403fb  brfalse  loc_40553
0x40400  ldarg.0
0x40401  call     instance bool System.Xml.Xsl.IlGen.IteratorDescriptor::get_HasLabelNext()
0x40406  brtrue.s loc_40448
0x40408  ldarg.0
0x40409  call     instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStack()
0x4040e  ldarg.0
0x4040f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x40414  ldc.i4.0
0x40415  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4041a  ldarg.0
0x4041b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x40420  ldarg.0
0x40421  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40426  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x4042b  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallCacheItem(class [mscorlib]System.Type itemStorageType)
0x40430  ldarg.0
0x40431  ldarg.0
0x40432  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40437  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x4043c  ldc.i4.0
0x4043d  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Stack(class [mscorlib]System.Type itemStorageType, bool isCached)
0x40442  stfld    valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40447  ret
0x40448  ldarg.0
0x40449  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x4044e  ldstr    aIdx// "$$$idx"
0x40453  ldtoken  [mscorlib]System.Int32
0x40458  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4045d  callvirt instance class [mscorlib]System.Reflection.Emit.LocalBuilder System.Xml.Xsl.IlGen.GenerateHelper::DeclareLocal(string name, class [mscorlib]System.Type type)
0x40462  stloc.0
0x40463  ldarg.0
0x40464  ldstr    aCache// "$$$cache"
0x40469  call     instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureNoStack(string locName)
0x4046e  ldarg.0
0x4046f  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x40474  ldc.i4.m1
0x40475  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4047a  ldarg.0
0x4047b  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x40480  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x40485  ldloc.0
0x40486  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x4048b  ldarg.0
0x4048c  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x40491  callvirt instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.GenerateHelper::DefineLabel()
0x40496  stloc.1
0x40497  ldarg.0
0x40498  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x4049d  ldloc.1
0x4049e  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::MarkLabel(valuetype [mscorlib]System.Reflection.Emit.Label lbl)
0x404a3  ldarg.0
0x404a4  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x404a9  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x404ae  ldloc.0
0x404af  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x404b4  ldarg.0
0x404b5  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x404ba  ldc.i4.1
0x404bb  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x404c0  ldarg.0
0x404c1  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x404c6  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Add
0x404cb  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode)
0x404d0  ldarg.0
0x404d1  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x404d6  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Stloc
0x404db  ldloc.0
0x404dc  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x404e1  ldarg.0
0x404e2  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x404e7  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x404ec  ldloc.0
0x404ed  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x404f2  ldarg.0
0x404f3  call     instance void System.Xml.Xsl.IlGen.IteratorDescriptor::CacheCount()
0x404f8  ldarg.0
0x404f9  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x404fe  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Bge
0x40503  ldarg.0
0x40504  call     instance valuetype [mscorlib]System.Reflection.Emit.Label System.Xml.Xsl.IlGen.IteratorDescriptor::GetLabelNext()
0x40509  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, valuetype [mscorlib]System.Reflection.Emit.Label lblVal)
0x4050e  ldarg.0
0x4050f  call     instance void System.Xml.Xsl.IlGen.IteratorDescriptor::PushValue()
0x40514  ldarg.0
0x40515  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x4051a  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldloc
0x4051f  ldloc.0
0x40520  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Reflection.Emit.LocalBuilder locBldr)
0x40525  ldarg.0
0x40526  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x4052b  ldarg.0
0x4052c  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40531  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x40536  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallCacheItem(class [mscorlib]System.Type itemStorageType)
0x4053b  ldarg.0
0x4053c  ldloc.1
0x4053d  ldarg.0
0x4053e  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40543  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x40548  ldc.i4.0
0x40549  call     valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::Stack(class [mscorlib]System.Type itemStorageType, bool isCached)
0x4054e  call     instance void System.Xml.Xsl.IlGen.IteratorDescriptor::SetIterator(valuetype [mscorlib]System.Reflection.Emit.Label lblNext, valuetype System.Xml.Xsl.IlGen.StorageDescriptor storage)
0x40553  ret
```
