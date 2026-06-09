# System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType

- ea: `0x40820`
- end: `0x40980`
- name: `System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureItemStorageType`
- size: `352`
- prototype: ``
- caller_count: `14`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x4b030`
- `0x4ba70`
- `0x4bdc0`
- `0x4c350`
- `0x4c770`
- `0x4cc30`
- `0x4d520`
- `0x4d740`
- `0x4e720`
- `0x4ee70`
- `0x504f0`
- `0x505b0`
- `0x50670`
- `0x50780`

## callees

- `0x3f060`
- `0x3f070`
- `0x3f180`
- `0x3f3e0`
- `0x3fce0`
- `0x40030`
- `0x40220`
- `0x40290`
- `0x402a0`
- `0x40670`
- `0x407e0`
- `0x40820`
- `0x40fa0`

## pseudocode

```c

```

## disassembly

```asm
0x40820  ldarg.0
0x40821  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40826  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x4082b  ldarg.2
0x4082c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x40831  brtrue   loc_4096D
0x40836  ldarg.0
0x40837  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x4083c  call     instance bool System.Xml.Xsl.IlGen.StorageDescriptor::get_IsCached()
0x40841  brfalse.s loc_408A7
0x40843  ldarg.0
0x40844  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40849  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x4084e  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x40853  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40858  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4085d  brfalse.s loc_4087A
0x4085f  ldarg.0
0x40860  call     instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStack()
0x40865  ldarg.0
0x40866  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x4086b  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::NavsToItems
0x40870  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x40875  br       loc_4096D
0x4087a  ldarg.2
0x4087b  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x40880  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x40885  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4088a  brfalse.s loc_408A7
0x4088c  ldarg.0
0x4088d  call     instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStack()
0x40892  ldarg.0
0x40893  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x40898  ldsfld   class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILMethods::ItemsToNavs
0x4089d  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x408a2  br       loc_4096D
0x408a7  ldarg.0
0x408a8  call     instance void System.Xml.Xsl.IlGen.IteratorDescriptor::EnsureStackNoCache()
0x408ad  ldarg.0
0x408ae  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x408b3  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x408b8  ldtoken  [System.Xml]System.Xml.XPath.XPathItem
0x408bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x408c2  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x408c7  brfalse.s loc_40905
0x408c9  ldarg.2
0x408ca  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x408cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x408d4  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x408d9  brfalse.s loc_408F7
0x408db  ldarg.0
0x408dc  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x408e1  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Castclass
0x408e6  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x408eb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x408f0  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode opcode, class [mscorlib]System.Type typVal)
0x408f5  br.s     loc_4096D
0x408f7  ldarg.0
0x408f8  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x408fd  ldarg.2
0x408fe  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::CallValueAs(class [mscorlib]System.Type clrType)
0x40903  br.s     loc_4096D
0x40905  ldarg.0
0x40906  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x4090b  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x40910  ldtoken  [System.Xml]System.Xml.XPath.XPathNavigator
0x40915  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4091a  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4091f  brtrue.s loc_4096D
0x40921  ldarg.0
0x40922  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x40927  ldarg.0
0x40928  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x4092d  callvirt instance class System.Xml.Xsl.IlGen.StaticDataManager System.Xml.Xsl.IlGen.GenerateHelper::get_StaticData()
0x40932  ldarg.1
0x40933  callvirt instance int32 System.Xml.Xsl.IlGen.StaticDataManager::DeclareXmlType(class System.Xml.Xsl.XmlQueryType type)
0x40938  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadInteger(int32 intVal)
0x4093d  ldarg.0
0x4093e  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x40943  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::LoadQueryRuntime()
0x40948  ldarg.0
0x40949  ldfld    class System.Xml.Xsl.IlGen.GenerateHelper System.Xml.Xsl.IlGen.IteratorDescriptor::helper
0x4094e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods> System.Xml.Xsl.IlGen.XmlILMethods::StorageMethods
0x40953  ldarg.0
0x40954  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40959  call     instance class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::get_ItemStorageType()
0x4095e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, class System.Xml.Xsl.IlGen.XmlILStorageMethods>::get_Item(void)
0x40963  ldfld    class [mscorlib]System.Reflection.MethodInfo System.Xml.Xsl.IlGen.XmlILStorageMethods::ToAtomicValue
0x40968  callvirt instance void System.Xml.Xsl.IlGen.GenerateHelper::Call(class [mscorlib]System.Reflection.MethodInfo meth)
0x4096d  ldarg.0
0x4096e  ldarg.0
0x4096f  ldflda   valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x40974  ldarg.2
0x40975  call     instance valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.StorageDescriptor::ToStorageType(class [mscorlib]System.Type itemStorageType)
0x4097a  stfld    valuetype System.Xml.Xsl.IlGen.StorageDescriptor System.Xml.Xsl.IlGen.IteratorDescriptor::storage
0x4097f  ret
```
