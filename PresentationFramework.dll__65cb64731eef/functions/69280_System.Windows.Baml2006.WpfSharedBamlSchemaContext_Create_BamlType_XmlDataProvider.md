# System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_XmlDataProvider

- ea: `0x69280`
- end: `0x692d5`
- name: `System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_XmlDataProvider`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x52080`
- `0x54760`

## callees

- `0x69280`
- `0x6a870`
- `0x6a8a0`
- `0x6a900`
- `0x6aa60`

## string_xrefs

- `0x692c3`: `XmlSerializer`
- `0x69286`: `XmlDataProvider`

## pseudocode

```c

```

## disassembly

```asm
0x69280  ldarg.0
0x69281  ldc.i4   0x2F2
0x69286  ldstr    aXmldataprovide// "XmlDataProvider"
0x6928b  ldtoken  System.Windows.Data.XmlDataProvider
0x69290  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x69295  ldarg.1
0x69296  ldarg.2
0x69297  newobj   instance void System.Windows.Baml2006.WpfKnownType::.ctor(class [System.Xaml]System.Xaml.XamlSchemaContext schema, int32 bamlNumber, string name, class [mscorlib]System.Type underlyingType, bool isBamlType, bool useV3Rules)
0x6929c  stloc.0
0x6929d  ldloc.0
0x6929e  ldsfld   class [mscorlib]System.Func`1<object> <>c::<>9__1152_0
0x692a3  dup
0x692a4  brtrue.s loc_692BD
0x692a6  pop
0x692a7  ldsfld   class <>c <>c::<>9
0x692ac  ldftn    instance object <>c::<Create_BamlType_XmlDataProvider>b__1152_0()
0x692b2  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x692b7  dup
0x692b8  stsfld   class [mscorlib]System.Func`1<object> <>c::<>9__1152_0
0x692bd  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DefaultConstructor(class [mscorlib]System.Func`1<object> value)
0x692c2  ldloc.0
0x692c3  ldstr    aXmlserializer// "XmlSerializer"
0x692c8  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_ContentPropertyName(string value)
0x692cd  ldloc.0
0x692ce  callvirt instance void System.Windows.Baml2006.WpfKnownType::Freeze()
0x692d3  ldloc.0
0x692d4  ret
```
