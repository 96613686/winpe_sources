# MS.Internal.Xaml.Runtime.DynamicMethodRuntime::CreateDelegateCreator

- ea: `0x1f1d0`
- end: `0x1f2c7`
- name: `MS.Internal.Xaml.Runtime.DynamicMethodRuntime::CreateDelegateCreator`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1efe0`

## callees

- `0x1f1d0`
- `0x1f2d0`
- `0x1f760`
- `0x1f880`
- `0x1f990`

## string_xrefs

- `0x1f1d1`: `_CreateDelegate`
- `0x1f27c`: `_CreateDelegate`

## pseudocode

```c

```

## disassembly

```asm
0x1f1d0  ldarg.1
0x1f1d1  ldstr    aCreatedelegate_0// "_CreateDelegate"
0x1f1d6  ldc.i4.s 0x26
0x1f1d8  ldnull
0x1f1d9  ldc.i4.2
0x1f1da  newarr   [mscorlib]System.Type
0x1f1df  dup
0x1f1e0  ldc.i4.0
0x1f1e1  ldtoken  [mscorlib]System.Type
0x1f1e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f1eb  stelem.ref
0x1f1ec  dup
0x1f1ed  ldc.i4.1
0x1f1ee  ldtoken  [mscorlib]System.String
0x1f1f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f1f8  stelem.ref
0x1f1f9  ldnull
0x1f1fa  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x1f1ff  stloc.0
0x1f200  ldloc.0
0x1f201  ldnull
0x1f202  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x1f207  brfalse.s loc_1F224
0x1f209  ldarg.0
0x1f20a  ldfld    class DelegateCreator MS.Internal.Xaml.Runtime.DynamicMethodRuntime::_delegateCreatorWithoutHelper
0x1f20f  brtrue.s loc_1F21D
0x1f211  ldarg.0
0x1f212  ldarg.0
0x1f213  call     instance class DelegateCreator MS.Internal.Xaml.Runtime.DynamicMethodRuntime::CreateDelegateCreatorWithoutHelper()
0x1f218  stfld    class DelegateCreator MS.Internal.Xaml.Runtime.DynamicMethodRuntime::_delegateCreatorWithoutHelper
0x1f21d  ldarg.0
0x1f21e  ldfld    class DelegateCreator MS.Internal.Xaml.Runtime.DynamicMethodRuntime::_delegateCreatorWithoutHelper
0x1f223  ret
0x1f224  ldarg.0
0x1f225  ldarg.1
0x1f226  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1f22b  ldstr    aDelegatehelper// "DelegateHelper"
0x1f230  call     string [mscorlib]System.String::Concat(string, string)
0x1f235  ldtoken  [mscorlib]System.Delegate
0x1f23a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f23f  ldc.i4.3
0x1f240  newarr   [mscorlib]System.Type
0x1f245  dup
0x1f246  ldc.i4.0
0x1f247  ldtoken  [mscorlib]System.Type
0x1f24c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f251  stelem.ref
0x1f252  dup
0x1f253  ldc.i4.1
0x1f254  ldtoken  [mscorlib]System.Object
0x1f259  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f25e  stelem.ref
0x1f25f  dup
0x1f260  ldc.i4.2
0x1f261  ldtoken  [mscorlib]System.String
0x1f266  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f26b  stelem.ref
0x1f26c  call     instance class [mscorlib]System.Reflection.Emit.DynamicMethod MS.Internal.Xaml.Runtime.DynamicMethodRuntime::CreateDynamicMethod(string name, class [mscorlib]System.Type returnType, class [mscorlib]System.Type[] argTypes)
0x1f271  stloc.1
0x1f272  ldloc.1
0x1f273  callvirt instance class [mscorlib]System.Reflection.Emit.ILGenerator [mscorlib]System.Reflection.Emit.DynamicMethod::GetILGenerator()
0x1f278  stloc.2
0x1f279  ldarg.0
0x1f27a  ldloc.2
0x1f27b  ldarg.1
0x1f27c  ldstr    aCreatedelegate_0// "_CreateDelegate"
0x1f281  ldc.i4   0x126
0x1f286  ldc.i4.1
0x1f287  ldc.i4.2
0x1f288  newarr   [mscorlib]System.Int16
0x1f28d  dup
0x1f28e  ldc.i4.1
0x1f28f  ldc.i4.2
0x1f290  stelem.i2
0x1f291  call     instance void MS.Internal.Xaml.Runtime.DynamicMethodRuntime::Emit_LateBoundInvoke(class [mscorlib]System.Reflection.Emit.ILGenerator ilGenerator, class [mscorlib]System.Type targetType, string methodName, valuetype [mscorlib]System.Reflection.BindingFlags bindingFlags, int16 targetArgNum, int16[] paramArgNums)
0x1f296  ldloc.2
0x1f297  ldtoken  [mscorlib]System.Delegate
0x1f29c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f2a1  call     void MS.Internal.Xaml.Runtime.DynamicMethodRuntime::Emit_CastTo(class [mscorlib]System.Reflection.Emit.ILGenerator ilGenerator, class [mscorlib]System.Type toType)
0x1f2a6  ldloc.2
0x1f2a7  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ret
0x1f2ac  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x1f2b1  ldloc.1
0x1f2b2  ldtoken  DelegateCreator
0x1f2b7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f2bc  callvirt instance class [mscorlib]System.Delegate [mscorlib]System.Reflection.MethodInfo::CreateDelegate(class [mscorlib]System.Type)
0x1f2c1  castclass DelegateCreator
0x1f2c6  ret
```
