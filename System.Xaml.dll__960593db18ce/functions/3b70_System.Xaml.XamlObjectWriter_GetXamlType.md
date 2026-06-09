# System.Xaml.XamlObjectWriter::GetXamlType

- ea: `0x3b70`
- end: `0x3bb0`
- name: `System.Xaml.XamlObjectWriter::GetXamlType`
- size: `64`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x2a90`
- `0x33d0`
- `0x3c80`
- `0x4770`
- `0x4940`
- `0x59c0`

## callees

- `0x3b70`
- `0xbcb0`
- `0xef20`
- `0xf3b0`
- `0x11f50`

## string_xrefs

- `0x3b86`: `ObjectWriterTypeNotAllowed`

## pseudocode

```c

```

## disassembly

```asm
0x3b70  ldarg.0
0x3b71  callvirt instance class System.Xaml.XamlSchemaContext System.Xaml.XamlWriter::get_SchemaContext()
0x3b76  ldarg.1
0x3b77  callvirt instance class System.Xaml.XamlType System.Xaml.XamlSchemaContext::GetXamlType(class [mscorlib]System.Type type)
0x3b7c  stloc.0
0x3b7d  ldloc.0
0x3b7e  ldnull
0x3b7f  call     bool System.Xaml.XamlType::op_Equality(class System.Xaml.XamlType xamlType1, class System.Xaml.XamlType xamlType2)
0x3b84  brfalse.s loc_3BAE
0x3b86  ldstr    aObjectwriterty// "ObjectWriterTypeNotAllowed"
0x3b8b  ldc.i4.2
0x3b8c  newarr   [mscorlib]System.Object
0x3b91  dup
0x3b92  ldc.i4.0
0x3b93  ldarg.0
0x3b94  callvirt instance class System.Xaml.XamlSchemaContext System.Xaml.XamlWriter::get_SchemaContext()
0x3b99  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3b9e  stelem.ref
0x3b9f  dup
0x3ba0  ldc.i4.1
0x3ba1  ldarg.1
0x3ba2  stelem.ref
0x3ba3  call     string System.Xaml.SR::Get(string id, object[] args)
0x3ba8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3bad  throw
0x3bae  ldloc.0
0x3baf  ret
```
