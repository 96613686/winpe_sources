# MS.Internal.Xaml.Runtime.DynamicMethodRuntime::GetValue

- ea: `0x1f0f0`
- end: `0x1f152`
- name: `MS.Internal.Xaml.Runtime.DynamicMethodRuntime::GetValue`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0xa400`
- `0x11f50`
- `0x19660`
- `0x1ee60`
- `0x1f0f0`
- `0x1f5e0`
- `0x1f7c0`
- `0x30760`

## string_xrefs

- `0x1f10b`: `CantGetWriteonlyProperty`

## pseudocode

```c

```

## disassembly

```asm
0x1f0f0  ldarg.0
0x1f0f1  call     instance void MS.Internal.Xaml.Runtime.DynamicMethodRuntime::DemandXamlLoadPermission()
0x1f0f6  ldarg.1
0x1f0f7  callvirt instance class System.Xaml.Schema.XamlMemberInvoker System.Xaml.XamlMember::get_Invoker()
0x1f0fc  callvirt instance class [mscorlib]System.Reflection.MethodInfo System.Xaml.Schema.XamlMemberInvoker::get_UnderlyingGetter()
0x1f101  stloc.0
0x1f102  ldloc.0
0x1f103  ldnull
0x1f104  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x1f109  brfalse.s loc_1F125
0x1f10b  ldstr    aCantgetwriteon// "CantGetWriteonlyProperty"
0x1f110  ldc.i4.1
0x1f111  newarr   [mscorlib]System.Object
0x1f116  dup
0x1f117  ldc.i4.0
0x1f118  ldarg.1
0x1f119  stelem.ref
0x1f11a  call     string System.Xaml.SR::Get(string id, object[] args)
0x1f11f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x1f124  throw
0x1f125  ldarg.0
0x1f126  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Reflection.MethodInfo, class PropertyGetDelegate> MS.Internal.Xaml.Runtime.DynamicMethodRuntime::get_PropertyGetDelegates()
0x1f12b  ldloc.0
0x1f12c  ldloca.s 1
0x1f12e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Reflection.MethodInfo, class PropertyGetDelegate>::TryGetValue(var<u1>, !!T0)
0x1f133  brtrue.s loc_1F14A
0x1f135  ldarg.0
0x1f136  ldloc.0
0x1f137  call     instance class PropertyGetDelegate MS.Internal.Xaml.Runtime.DynamicMethodRuntime::CreateGetDelegate(class [mscorlib]System.Reflection.MethodInfo getter)
0x1f13c  stloc.1
0x1f13d  ldarg.0
0x1f13e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Reflection.MethodInfo, class PropertyGetDelegate> MS.Internal.Xaml.Runtime.DynamicMethodRuntime::get_PropertyGetDelegates()
0x1f143  ldloc.0
0x1f144  ldloc.1
0x1f145  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Reflection.MethodInfo, class PropertyGetDelegate>::Add(var<u1>, !!T0)
0x1f14a  ldloc.1
0x1f14b  ldarg.2
0x1f14c  callvirt instance object PropertyGetDelegate::Invoke(object target)
0x1f151  ret
```
