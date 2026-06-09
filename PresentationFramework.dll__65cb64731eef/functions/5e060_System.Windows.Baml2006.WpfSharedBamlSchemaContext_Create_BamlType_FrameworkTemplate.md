# System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_FrameworkTemplate

- ea: `0x5e060`
- end: `0x5e090`
- name: `System.Windows.Baml2006.WpfSharedBamlSchemaContext::Create_BamlType_FrameworkTemplate`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x52080`
- `0x54760`

## callees

- `0x6a870`
- `0x6a8a0`
- `0x6a900`

## string_xrefs

- `0x5e07e`: `Template`
- `0x5e066`: `FrameworkTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x5e060  ldarg.0
0x5e061  ldc.i4   0xE7
0x5e066  ldstr    aFrameworktempl// "FrameworkTemplate"
0x5e06b  ldtoken  System.Windows.FrameworkTemplate
0x5e070  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5e075  ldarg.1
0x5e076  ldarg.2
0x5e077  newobj   instance void System.Windows.Baml2006.WpfKnownType::.ctor(class [System.Xaml]System.Xaml.XamlSchemaContext schema, int32 bamlNumber, string name, class [mscorlib]System.Type underlyingType, bool isBamlType, bool useV3Rules)
0x5e07c  stloc.0
0x5e07d  ldloc.0
0x5e07e  ldstr    aTemplate// "Template"
0x5e083  callvirt instance void System.Windows.Baml2006.WpfKnownType::set_ContentPropertyName(string value)
0x5e088  ldloc.0
0x5e089  callvirt instance void System.Windows.Baml2006.WpfKnownType::Freeze()
0x5e08e  ldloc.0
0x5e08f  ret
```
