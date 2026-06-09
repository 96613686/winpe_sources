# System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_HierarchicalDataTemplate

- ea: `0x5ee80`
- end: `0x5eee0`
- name: `System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_HierarchicalDataTemplate`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x52080`
- `0x54760`

## callees

- `0x5ee80`
- `0x6a870`
- `0x6a8a0`
- `0x6a900`
- `0x6aa00`
- `0x6aa60`

## string_xrefs

- `0x5eec3`: `Template`
- `0x5eece`: `DataTemplateKey`
- `0x5ee86`: `HierarchicalDataTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5ee80  ldarg.0
0x5ee81  ldc.i4   0x10F
0x5ee86  ldstr    aHierarchicalda// "HierarchicalDataTemplate"
0x5ee8b  ldtoken  System.Windows.HierarchicalDataTemplate
0x5ee90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ee95  ldarg.1
0x5ee96  ldarg.2
0x5ee97  newobj   instance void System.Windows.Baml2006.WpfKnownType::.ctor(class [System.Xaml]System.Xaml.XamlSchemaContext schema, int32 bamlNumber, string name, class [mscorlib]System.Type underlyingType, bool isBamlType, bool useV3Rules)
0x5ee9c  stloc.0
0x5ee9d  ldloc.0
0x5ee9e  ldsfld   class [mscorlib]System.Func`1<object> <>c::<>9__669_0
0x5eea3  dup
0x5eea4  brtrue.s loc_5EEBD
0x5eea6  pop
0x5eea7  ldsfld   class <>c <>c::<>9
0x5eeac  ldftn    instance object <>c::<Create_BamlType_HierarchicalDataTemplate>b__669_0()
0x5eeb2  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x5eeb7  dup
0x5eeb8  stsfld   class [mscorlib]System.Func`1<object> <>c::<>9__669_0
0x5eebd  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DefaultConstructor(class [mscorlib]System.Func`1<object> value)
0x5eec2  ldloc.0
0x5eec3  ldstr    aTemplate// "Template"
0x5eec8  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_ContentPropertyName(string value)
0x5eecd  ldloc.0
0x5eece  ldstr    aDatatemplateke// "DataTemplateKey"
0x5eed3  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DictionaryKeyPropertyName(string value)
0x5eed8  ldloc.0
0x5eed9  callvirt instance void System.Windows.Baml2006.WpfKnownType::Freeze()
0x5eede  ldloc.0
0x5eedf  ret
```
