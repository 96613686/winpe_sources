# SerializerContext::GetXamlType

- ea: `0x2bf00`
- end: `0x2bf40`
- name: `SerializerContext::GetXamlType`
- size: `64`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x29510`
- `0x29670`
- `0x2a8b0`
- `0x2ab30`
- `0x2b3b0`
- `0x2b4a0`
- `0x2bc10`
- `0x2bf40`
- `0x2c060`
- `0x2c160`

## callees

- `0x8810`
- `0xbcb0`
- `0xef20`
- `0x11f50`
- `0x2bf00`

## string_xrefs

- `0x2bf16`: `ObjectReaderTypeNotAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x2bf00  ldarg.0
0x2bf01  ldfld    class System.Xaml.XamlSchemaContext SerializerContext::schemaContext
0x2bf06  ldarg.1
0x2bf07  callvirt instance class System.Xaml.XamlType System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type type)
0x2bf0c  stloc.0
0x2bf0d  ldloc.0
0x2bf0e  ldnull
0x2bf0f  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x2bf14  brfalse.s loc_2BF3E
0x2bf16  ldstr    aObjectreaderty_1// "ObjectReaderTypeNotAllowed"
0x2bf1b  ldc.i4.2
0x2bf1c  newarr   [mscorlib]System.Object
0x2bf21  dup
0x2bf22  ldc.i4.0
0x2bf23  ldarg.0
0x2bf24  ldfld    class System.Xaml.XamlSchemaContext SerializerContext::schemaContext
0x2bf29  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2bf2e  stelem.ref
0x2bf2f  dup
0x2bf30  ldc.i4.1
0x2bf31  ldarg.1
0x2bf32  stelem.ref
0x2bf33  call     string System.Xaml.SR::Get(string id, object[] args)
0x2bf38  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2bf3d  throw
0x2bf3e  ldloc.0
0x2bf3f  ret
```
