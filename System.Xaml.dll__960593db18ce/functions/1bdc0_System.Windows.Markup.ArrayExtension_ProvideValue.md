# System.Windows.Markup.ArrayExtension::ProvideValue

- ea: `0x1bdc0`
- end: `0x1be1b`
- name: `System.Windows.Markup.ArrayExtension::ProvideValue`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x11f20`
- `0x11f50`
- `0x1bdc0`

## string_xrefs

- `0x1bdce`: `MarkupExtensionArrayType`
- `0x1bdf5`: `MarkupExtensionArrayBadType`

## pseudocode

```c

```

## disassembly

```asm
0x1bdc0  ldarg.0
0x1bdc1  ldfld    class [mscorlib]System.Type System.Windows.Markup.ArrayExtension::_arrayType
0x1bdc6  ldnull
0x1bdc7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1bdcc  brfalse.s loc_1BDDE
0x1bdce  ldstr    aMarkupextensio_0// "MarkupExtensionArrayType"
0x1bdd3  call     string System.Xaml.SR::Get(string id)
0x1bdd8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1bddd  throw
0x1bdde  ldnull
0x1bddf  stloc.0
0x1bde0  ldarg.0
0x1bde1  ldfld    class [mscorlib]System.Collections.ArrayList System.Windows.Markup.ArrayExtension::_arrayList
0x1bde6  ldarg.0
0x1bde7  ldfld    class [mscorlib]System.Type System.Windows.Markup.ArrayExtension::_arrayType
0x1bdec  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x1bdf1  stloc.0
0x1bdf2  leave.s  loc_1BE19
0x1bdf4  pop
0x1bdf5  ldstr    aMarkupextensio_1// "MarkupExtensionArrayBadType"
0x1bdfa  ldc.i4.1
0x1bdfb  newarr   [mscorlib]System.Object
0x1be00  dup
0x1be01  ldc.i4.0
0x1be02  ldarg.0
0x1be03  ldfld    class [mscorlib]System.Type System.Windows.Markup.ArrayExtension::_arrayType
0x1be08  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1be0d  stelem.ref
0x1be0e  call     string System.Xaml.SR::Get(string id, object[] args)
0x1be13  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1be18  throw
0x1be19  ldloc.0
0x1be1a  ret
```
