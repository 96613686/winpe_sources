# System.Xaml.Schema.XamlMemberInvoker::GetValue

- ea: `0x196a0`
- end: `0x196e9`
- name: `System.Xaml.Schema.XamlMemberInvoker::GetValue`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1e710`

## callees

- `0x11f50`
- `0x19660`
- `0x196a0`
- `0x196f0`
- `0x19940`

## string_xrefs

- `0x196c2`: `CantGetWriteonlyProperty`

## pseudocode

```c

```

## disassembly

```asm
0x196a0  ldarg.1
0x196a1  brtrue.s loc_196AE
0x196a3  ldstr    aInstance// "instance"
0x196a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x196ad  throw
0x196ae  ldarg.0
0x196af  call     instance void System.Xaml.Schema.XamlMemberInvoker::ThrowIfUnknown()
0x196b4  ldarg.0
0x196b5  call     instance class [mscorlib]System.Reflection.MethodInfo System.Xaml.Schema.XamlMemberInvoker::get_UnderlyingGetter()
0x196ba  ldnull
0x196bb  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x196c0  brfalse.s loc_196E1
0x196c2  ldstr    aCantgetwriteon// "CantGetWriteonlyProperty"
0x196c7  ldc.i4.1
0x196c8  newarr   [mscorlib]System.Object
0x196cd  dup
0x196ce  ldc.i4.0
0x196cf  ldarg.0
0x196d0  ldfld    class System.Xaml.XamlMember System.Xaml.Schema.XamlMemberInvoker::_member
0x196d5  stelem.ref
0x196d6  call     string System.Xaml.SR::Get(string id, object[] args)
0x196db  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x196e0  throw
0x196e1  ldarg.0
0x196e2  ldarg.1
0x196e3  call     instance object System.Xaml.Schema.XamlMemberInvoker::GetValueSafeCritical(object instance)
0x196e8  ret
```
