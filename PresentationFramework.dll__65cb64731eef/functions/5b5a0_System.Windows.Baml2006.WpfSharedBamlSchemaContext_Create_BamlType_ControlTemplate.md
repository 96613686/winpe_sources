# System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_ControlTemplate

- ea: `0x5b5a0`
- end: `0x5b5fd`
- name: `System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_ControlTemplate`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x52080`
- `0x54760`

## callees

- `0x5b5a0`
- `0x6a870`
- `0x6a8a0`
- `0x6a900`
- `0x6aa00`
- `0x6aa60`

## string_xrefs

- `0x5b5e0`: `Template`
- `0x5b5a3`: `ControlTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5b5a0  ldarg.0
0x5b5a1  ldc.i4.s 0x6C
0x5b5a3  ldstr    aControltemplat// "ControlTemplate"
0x5b5a8  ldtoken  System.Windows.Controls.ControlTemplate
0x5b5ad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5b5b2  ldarg.1
0x5b5b3  ldarg.2
0x5b5b4  newobj   instance void System.Windows.Baml2006.WpfKnownType::.ctor(class [System.Xaml]System.Xaml.XamlSchemaContext schema, int32 bamlNumber, string name, class [mscorlib]System.Type underlyingType, bool isBamlType, bool useV3Rules)
0x5b5b9  stloc.0
0x5b5ba  ldloc.0
0x5b5bb  ldsfld   class [mscorlib]System.Func`1<object> <>c::<>9__506_0
0x5b5c0  dup
0x5b5c1  brtrue.s loc_5B5DA
0x5b5c3  pop
0x5b5c4  ldsfld   class <>c <>c::<>9
0x5b5c9  ldftn    instance object <>c::<Create_BamlType_ControlTemplate>b__506_0()
0x5b5cf  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x5b5d4  dup
0x5b5d5  stsfld   class [mscorlib]System.Func`1<object> <>c::<>9__506_0
0x5b5da  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DefaultConstructor(class [mscorlib]System.Func`1<object> value)
0x5b5df  ldloc.0
0x5b5e0  ldstr    aTemplate// "Template"
0x5b5e5  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_ContentPropertyName(string value)
0x5b5ea  ldloc.0
0x5b5eb  ldstr    aTargettype_0// "TargetType"
0x5b5f0  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DictionaryKeyPropertyName(string value)
0x5b5f5  ldloc.0
0x5b5f6  callvirt instance void System.Windows.Baml2006.WpfKnownType::Freeze()
0x5b5fb  ldloc.0
0x5b5fc  ret
```
