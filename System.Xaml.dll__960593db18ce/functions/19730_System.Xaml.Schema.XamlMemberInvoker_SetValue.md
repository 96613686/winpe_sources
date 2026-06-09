# System.Xaml.Schema.XamlMemberInvoker::SetValue

- ea: `0x19730`
- end: `0x1977a`
- name: `System.Xaml.Schema.XamlMemberInvoker::SetValue`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1e770`

## callees

- `0x11f50`
- `0x19680`
- `0x19730`
- `0x19780`
- `0x19940`

## string_xrefs

- `0x19752`: `CantSetReadonlyProperty`

## pseudocode

```c

```

## disassembly

```asm
0x19730  ldarg.1
0x19731  brtrue.s loc_1973E
0x19733  ldstr    aInstance// "instance"
0x19738  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1973d  throw
0x1973e  ldarg.0
0x1973f  call     instance void System.Xaml.Schema.XamlMemberInvoker::ThrowIfUnknown()
0x19744  ldarg.0
0x19745  call     instance class [mscorlib]System.Reflection.MethodInfo System.Xaml.Schema.XamlMemberInvoker::get_UnderlyingSetter()
0x1974a  ldnull
0x1974b  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x19750  brfalse.s loc_19771
0x19752  ldstr    aCantsetreadonl// "CantSetReadonlyProperty"
0x19757  ldc.i4.1
0x19758  newarr   [mscorlib]System.Object
0x1975d  dup
0x1975e  ldc.i4.0
0x1975f  ldarg.0
0x19760  ldfld    class System.Xaml.XamlMember System.Xaml.Schema.XamlMemberInvoker::_member
0x19765  stelem.ref
0x19766  call     string System.Xaml.SR::Get(string id, object[] args)
0x1976b  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x19770  throw
0x19771  ldarg.0
0x19772  ldarg.1
0x19773  ldarg.2
0x19774  call     instance void System.Xaml.Schema.XamlMemberInvoker::SetValueSafeCritical(object instance, object value)
0x19779  ret
```
