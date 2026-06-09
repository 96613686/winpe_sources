# SerializerContext::LocalAssemblyAwareGetXamlType

- ea: `0x2bf40`
- end: `0x2bf89`
- name: `SerializerContext::LocalAssemblyAwareGetXamlType`
- size: `73`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x2b0e0`
- `0x2b220`
- `0x2b240`
- `0x2b6a0`
- `0x2b740`

## callees

- `0x8810`
- `0xd8f0`
- `0x11f50`
- `0x2bd50`
- `0x2bf00`
- `0x2bf40`

## string_xrefs

- `0x2bf68`: `ObjectReader_TypeNotVisible`

## pseudocode

```c

```

## disassembly

```asm
0x2bf40  ldarg.0
0x2bf41  ldarg.1
0x2bf42  call     instance class System.Xaml.XamlType SerializerContext::GetXamlType(class [mscorlib]System.Type clrType)
0x2bf47  stloc.0
0x2bf48  ldloc.0
0x2bf49  ldarg.0
0x2bf4a  call     instance class [mscorlib]System.Reflection.Assembly SerializerContext::get_LocalAssembly()
0x2bf4f  callvirt instance bool System.Xaml.XamlType::IsVisibleTo(class [mscorlib]System.Reflection.Assembly accessingAssembly)
0x2bf54  brtrue.s loc_2BF87
0x2bf56  ldtoken  [mscorlib]System.Type
0x2bf5b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2bf60  ldarg.1
0x2bf61  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x2bf66  brtrue.s loc_2BF87
0x2bf68  ldstr    aObjectreaderTy// "ObjectReader_TypeNotVisible"
0x2bf6d  ldc.i4.1
0x2bf6e  newarr   [mscorlib]System.Object
0x2bf73  dup
0x2bf74  ldc.i4.0
0x2bf75  ldarg.1
0x2bf76  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2bf7b  stelem.ref
0x2bf7c  call     string System.Xaml.SR::Get(string id, object[] args)
0x2bf81  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2bf86  throw
0x2bf87  ldloc.0
0x2bf88  ret
```
