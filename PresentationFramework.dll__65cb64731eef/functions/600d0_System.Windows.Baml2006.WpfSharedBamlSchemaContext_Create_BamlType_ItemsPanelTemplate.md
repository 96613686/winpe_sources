# System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_ItemsPanelTemplate

- ea: `0x600d0`
- end: `0x60125`
- name: `System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_ItemsPanelTemplate`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x52080`
- `0x54760`

## callees

- `0x600d0`
- `0x6a870`
- `0x6a8a0`
- `0x6a900`
- `0x6aa60`

## string_xrefs

- `0x60113`: `Template`
- `0x600d6`: `ItemsPanelTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x600d0  ldarg.0
0x600d1  ldc.i4   0x14A
0x600d6  ldstr    aItemspaneltemp// "ItemsPanelTemplate"
0x600db  ldtoken  System.Windows.Controls.ItemsPanelTemplate
0x600e0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x600e5  ldarg.1
0x600e6  ldarg.2
0x600e7  newobj   instance void System.Windows.Baml2006.WpfKnownType::.ctor(class [System.Xaml]System.Xaml.XamlSchemaContext schema, int32 bamlNumber, string name, class [mscorlib]System.Type underlyingType, bool isBamlType, bool useV3Rules)
0x600ec  stloc.0
0x600ed  ldloc.0
0x600ee  ldsfld   class [mscorlib]System.Func`1<object> <>c::<>9__728_0
0x600f3  dup
0x600f4  brtrue.s loc_6010D
0x600f6  pop
0x600f7  ldsfld   class <>c <>c::<>9
0x600fc  ldftn    instance object <>c::<Create_BamlType_ItemsPanelTemplate>b__728_0()
0x60102  newobj   instance void class [mscorlib]System.Func`1<object>::.ctor(object, native int)
0x60107  dup
0x60108  stsfld   class [mscorlib]System.Func`1<object> <>c::<>9__728_0
0x6010d  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_DefaultConstructor(class [mscorlib]System.Func`1<object> value)
0x60112  ldloc.0
0x60113  ldstr    aTemplate// "Template"
0x60118  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_ContentPropertyName(string value)
0x6011d  ldloc.0
0x6011e  callvirt instance void System.Windows.Baml2006.WpfKnownType::Freeze()
0x60123  ldloc.0
0x60124  ret
```
