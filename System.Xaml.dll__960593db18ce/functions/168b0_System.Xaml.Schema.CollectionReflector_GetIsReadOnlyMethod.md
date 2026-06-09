# System.Xaml.Schema.CollectionReflector::GetIsReadOnlyMethod

- ea: `0x168b0`
- end: `0x168e8`
- name: `System.Xaml.Schema.CollectionReflector::GetIsReadOnlyMethod`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0xd740`

## callees

- `0x168b0`

## string_xrefs

- `0x168d4`: `IsReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x168b0  ldtoken  [mscorlib]System.Collections.Generic.ICollection`1
0x168b5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x168ba  ldc.i4.1
0x168bb  newarr   [mscorlib]System.Type
0x168c0  dup
0x168c1  ldc.i4.0
0x168c2  ldarg.1
0x168c3  stelem.ref
0x168c4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::MakeGenericType(class [mscorlib]System.Type[])
0x168c9  stloc.0
0x168ca  ldloc.0
0x168cb  ldarg.0
0x168cc  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x168d1  brfalse.s loc_168E6
0x168d3  ldloc.0
0x168d4  ldstr    aIsreadonly// "IsReadOnly"
0x168d9  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x168de  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Reflection.PropertyInfo::GetGetMethod()
0x168e3  stloc.1
0x168e4  ldloc.1
0x168e5  ret
0x168e6  ldnull
0x168e7  ret
```
