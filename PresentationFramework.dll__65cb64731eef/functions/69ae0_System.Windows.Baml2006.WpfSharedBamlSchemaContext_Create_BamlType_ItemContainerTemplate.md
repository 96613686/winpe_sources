# System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_ItemContainerTemplate

- ea: `0x69ae0`
- end: `0x69b3c`
- name: `System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_ItemContainerTemplate`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x54760`

## callees

- `0x69ae0`
- `0x6a870`
- `0x6a8a0`
- `0x6a900`
- `0x6aa00`
- `0x6aa60`

## string_xrefs

- `0x69b1f`: `Template`
- `0x69ae2`: `ItemContainerTemplate`
- `0x69b2a`: `ItemContainerTemplateKey`

## pseudocode

```c

```

## disassembly

```asm
0x69ae0  ldarg.0
0x69ae1  ldc.i4.0
0x69ae2  ldstr    aItemcontainert// "ItemContainerTemplate"
0x69ae7  ldtoken  System.Windows.Controls.ItemContainerTemplate
0x69aec  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69af1  ldarg.1
0x69af2  ldarg.2
0x69af3  newobj   instance void System.Windows.Baml2006.WpfKnownType::.ctor(class [System.Xaml]System.Xaml.XamlSchemaContext schema, int32 bamlNumber, string name, class [mscorlib]System.Type underlyingType, bool isBamlType, bool useV3Rules)
0x69af8  stloc.0
0x69af9  ldloc.0
0x69afa  ldsfld   class [mscorlib]System.Func`1<object> <>c::<>9__1180_0
0x69aff  dup
0x69b00  brtrue.s loc_69B19
0x69b02  pop
0x69b03  ldsfld   class <>c <>c::<>9
0x69b08  ldftn    instance object <>c::<Create_BamlType_ItemContainerTemplate>b__1180_0()
0x69b0e  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x69b13  dup
0x69b14  stsfld   class [mscorlib]System.Func`1<object> <>c::<>9__1180_0
0x69b19  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DefaultConstructor(class [mscorlib]System.Func`1<object> value)
0x69b1e  ldloc.0
0x69b1f  ldstr    aTemplate// "Template"
0x69b24  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_ContentPropertyName(string value)
0x69b29  ldloc.0
0x69b2a  ldstr    aItemcontainert_0// "ItemContainerTemplateKey"
0x69b2f  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DictionaryKeyPropertyName(string value)
0x69b34  ldloc.0
0x69b35  callvirt instance void System.Windows.Baml2006.WpfKnownType::Freeze()
0x69b3a  ldloc.0
0x69b3b  ret
```
