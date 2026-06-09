# MS.Internal.Xaml.Runtime.DynamicMethodRuntime::CreateDelegateCreatorWithoutHelper

- ea: `0x1f2d0`
- end: `0x1f3ae`
- name: `MS.Internal.Xaml.Runtime.DynamicMethodRuntime::CreateDelegateCreatorWithoutHelper`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f1d0`

## callees

- `0x1f760`

## string_xrefs

- `0x1f345`: `CreateDelegate`
- `0x1f2d1`: `CreateDelegateHelper`

## pseudocode

```c

```

## disassembly

```asm
0x1f2d0  ldarg.0
0x1f2d1  ldstr    aCreatedelegate_1// "CreateDelegateHelper"
0x1f2d6  ldtoken  [mscorlib]System.Delegate
0x1f2db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f2e0  ldc.i4.3
0x1f2e1  newarr   [mscorlib]System.Type
0x1f2e6  dup
0x1f2e7  ldc.i4.0
0x1f2e8  ldtoken  [mscorlib]System.Type
0x1f2ed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f2f2  stelem.ref
0x1f2f3  dup
0x1f2f4  ldc.i4.1
0x1f2f5  ldtoken  [mscorlib]System.Object
0x1f2fa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f2ff  stelem.ref
0x1f300  dup
0x1f301  ldc.i4.2
0x1f302  ldtoken  [mscorlib]System.String
0x1f307  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f30c  stelem.ref
0x1f30d  call     instance class [mscorlib]System.Reflection.Emit.DynamicMethod MS.Internal.Xaml.Runtime.DynamicMethodRuntime::CreateDynamicMethod(string name, class [mscorlib]System.Type returnType, class [mscorlib]System.Type[] argTypes)
0x1f312  stloc.0
0x1f313  ldloc.0
0x1f314  callvirt instance class [mscorlib]System.Reflection.Emit.ILGenerator [mscorlib]System.Reflection.Emit.DynamicMethod::GetILGenerator()
0x1f319  stloc.1
0x1f31a  ldloc.1
0x1f31b  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_0
0x1f320  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x1f325  ldloc.1
0x1f326  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_1
0x1f32b  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x1f330  ldloc.1
0x1f331  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_2
0x1f336  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x1f33b  ldtoken  [mscorlib]System.Delegate
0x1f340  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f345  ldstr    aCreatedelegate// "CreateDelegate"
0x1f34a  ldc.i4.s 0x18
0x1f34c  ldnull
0x1f34d  ldc.i4.3
0x1f34e  newarr   [mscorlib]System.Type
0x1f353  dup
0x1f354  ldc.i4.0
0x1f355  ldtoken  [mscorlib]System.Type
0x1f35a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f35f  stelem.ref
0x1f360  dup
0x1f361  ldc.i4.1
0x1f362  ldtoken  [mscorlib]System.Object
0x1f367  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f36c  stelem.ref
0x1f36d  dup
0x1f36e  ldc.i4.2
0x1f36f  ldtoken  [mscorlib]System.String
0x1f374  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f379  stelem.ref
0x1f37a  ldnull
0x1f37b  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x1f380  stloc.2
0x1f381  ldloc.1
0x1f382  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Call
0x1f387  ldloc.2
0x1f388  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode, class [mscorlib]System.Reflection.MethodInfo)
0x1f38d  ldloc.1
0x1f38e  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ret
0x1f393  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x1f398  ldloc.0
0x1f399  ldtoken  DelegateCreator
0x1f39e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f3a3  callvirt instance class [mscorlib]System.Delegate [mscorlib]System.Reflection.MethodInfo::CreateDelegate(class [mscorlib]System.Type)
0x1f3a8  castclass DelegateCreator
0x1f3ad  ret
```
