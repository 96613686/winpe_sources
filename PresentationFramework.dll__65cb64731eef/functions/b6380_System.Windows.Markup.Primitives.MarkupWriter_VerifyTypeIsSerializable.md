# System.Windows.Markup.Primitives.MarkupWriter::VerifyTypeIsSerializable

- ea: `0xb6380`
- end: `0xb63f6`
- name: `System.Windows.Markup.Primitives.MarkupWriter::VerifyTypeIsSerializable`
- size: `118`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0xb5df0`
- `0xb6530`
- `0xb6590`

## callees

- `0x38c70`
- `0xb6380`

## string_xrefs

- `0xb6388`: `MarkupWriter_CannotSerializeNestedPublictype`
- `0xb63af`: `MarkupWriter_CannotSerializeNonPublictype`
- `0xb63d6`: `MarkupWriter_CannotSerializeGenerictype`

## pseudocode

```c

```

## disassembly

```asm
0xb6380  ldarg.0
0xb6381  callvirt instance bool [mscorlib]System.Type::get_IsNestedPublic()
0xb6386  brfalse.s loc_B63A7
0xb6388  ldstr    aMarkupwriterCa// "MarkupWriter_CannotSerializeNestedPubli"...
0xb638d  ldc.i4.1
0xb638e  newarr   [mscorlib]System.Object
0xb6393  dup
0xb6394  ldc.i4.0
0xb6395  ldarg.0
0xb6396  callvirt instance string [mscorlib]System.Object::ToString()
0xb639b  stelem.ref
0xb639c  call     string System.Windows.SR::Get(string id, object[] args)
0xb63a1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb63a6  throw
0xb63a7  ldarg.0
0xb63a8  callvirt instance bool [mscorlib]System.Type::get_IsPublic()
0xb63ad  brtrue.s loc_B63CE
0xb63af  ldstr    aMarkupwriterCa_0// "MarkupWriter_CannotSerializeNonPublicty"...
0xb63b4  ldc.i4.1
0xb63b5  newarr   [mscorlib]System.Object
0xb63ba  dup
0xb63bb  ldc.i4.0
0xb63bc  ldarg.0
0xb63bd  callvirt instance string [mscorlib]System.Object::ToString()
0xb63c2  stelem.ref
0xb63c3  call     string System.Windows.SR::Get(string id, object[] args)
0xb63c8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb63cd  throw
0xb63ce  ldarg.0
0xb63cf  callvirt instance bool [mscorlib]System.Type::get_IsGenericType()
0xb63d4  brfalse.s loc_B63F5
0xb63d6  ldstr    aMarkupwriterCa_1// "MarkupWriter_CannotSerializeGenerictype"
0xb63db  ldc.i4.1
0xb63dc  newarr   [mscorlib]System.Object
0xb63e1  dup
0xb63e2  ldc.i4.0
0xb63e3  ldarg.0
0xb63e4  callvirt instance string [mscorlib]System.Object::ToString()
0xb63e9  stelem.ref
0xb63ea  call     string System.Windows.SR::Get(string id, object[] args)
0xb63ef  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb63f4  throw
0xb63f5  ret
```
