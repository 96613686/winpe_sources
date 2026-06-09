# System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_DataTemplate

- ea: `0x5b930`
- end: `0x5b98d`
- name: `System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_DataTemplate`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x52080`
- `0x54760`

## callees

- `0x5b930`
- `0x6a870`
- `0x6a8a0`
- `0x6a900`
- `0x6aa00`
- `0x6aa60`

## string_xrefs

- `0x5b970`: `Template`
- `0x5b97b`: `DataTemplateKey`
- `0x5b933`: `DataTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5b930  ldarg.0
0x5b931  ldc.i4.s 0x78
0x5b933  ldstr    aDatatemplate// "DataTemplate"
0x5b938  ldtoken  System.Windows.DataTemplate
0x5b93d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5b942  ldarg.1
0x5b943  ldarg.2
0x5b944  newobj   instance void System.Windows.Baml2006.WpfKnownType::.ctor(class [System.Xaml]System.Xaml.XamlSchemaContext schema, int32 bamlNumber, string name, class [mscorlib]System.Type underlyingType, bool isBamlType, bool useV3Rules)
0x5b949  stloc.0
0x5b94a  ldloc.0
0x5b94b  ldsfld   class [mscorlib]System.Func`1<object> <>c::<>9__518_0
0x5b950  dup
0x5b951  brtrue.s loc_5B96A
0x5b953  pop
0x5b954  ldsfld   class <>c <>c::<>9
0x5b959  ldftn    instance object <>c::<Create_BamlType_DataTemplate>b__518_0()
0x5b95f  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x5b964  dup
0x5b965  stsfld   class [mscorlib]System.Func`1<object> <>c::<>9__518_0
0x5b96a  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DefaultConstructor(class [mscorlib]System.Func`1<object> value)
0x5b96f  ldloc.0
0x5b970  ldstr    aTemplate// "Template"
0x5b975  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_ContentPropertyName(string value)
0x5b97a  ldloc.0
0x5b97b  ldstr    aDatatemplateke// "DataTemplateKey"
0x5b980  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DictionaryKeyPropertyName(string value)
0x5b985  ldloc.0
0x5b986  callvirt instance void System.Windows.Baml2006.WpfKnownType::Freeze()
0x5b98b  ldloc.0
0x5b98c  ret
```
