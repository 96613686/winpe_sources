# System.Xaml.Schema.SafeReflectionInvoker::CreateDynamicAssembly

- ea: `0x17c80`
- end: `0x1801b`
- name: `System.Xaml.Schema.SafeReflectionInvoker::CreateDynamicAssembly`
- size: `923`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x17c20`

## string_xrefs

- `0x17cc4`: `CreateDelegate`
- `0x17cd0`: `CreateDelegate`
- `0x17da9`: `CreateDelegate`
- `0x17db5`: `CreateDelegate`
- `0x17e81`: `CreateInstance`
- `0x17e8d`: `CreateInstance`

## pseudocode

```c

```

## disassembly

```asm
0x17c80  ldc.i4.s 0x20
0x17c82  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x17c87  call     instance void [mscorlib]System.Security.CodeAccessPermission::Assert()
0x17c8c  ldc.i4.3
0x17c8d  newarr   [mscorlib]System.Type
0x17c92  dup
0x17c93  ldc.i4.0
0x17c94  ldtoken  [mscorlib]System.Type
0x17c99  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17c9e  stelem.ref
0x17c9f  dup
0x17ca0  ldc.i4.1
0x17ca1  ldtoken  [mscorlib]System.Type
0x17ca6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17cab  stelem.ref
0x17cac  dup
0x17cad  ldc.i4.2
0x17cae  ldtoken  [mscorlib]System.String
0x17cb3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17cb8  stelem.ref
0x17cb9  stloc.0
0x17cba  ldtoken  [mscorlib]System.Delegate
0x17cbf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17cc4  ldstr    aCreatedelegate// "CreateDelegate"
0x17cc9  ldloc.0
0x17cca  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x17ccf  stloc.2
0x17cd0  ldstr    aCreatedelegate// "CreateDelegate"
0x17cd5  ldtoken  [mscorlib]System.Delegate
0x17cda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17cdf  ldloc.0
0x17ce0  newobj   instance void [mscorlib]System.Reflection.Emit.DynamicMethod::.ctor(string, class [mscorlib]System.Type, class [mscorlib]System.Type[])
0x17ce5  stloc.3
0x17ce6  ldloc.3
0x17ce7  ldc.i4.1
0x17ce8  ldc.i4.1
0x17ce9  ldstr    aDelegatetype// "delegateType"
0x17cee  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17cf3  pop
0x17cf4  ldloc.3
0x17cf5  ldc.i4.2
0x17cf6  ldc.i4.1
0x17cf7  ldstr    aTargettype// "targetType"
0x17cfc  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17d01  pop
0x17d02  ldloc.3
0x17d03  ldc.i4.3
0x17d04  ldc.i4.1
0x17d05  ldstr    aMethodname// "methodName"
0x17d0a  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17d0f  pop
0x17d10  ldloc.3
0x17d11  ldc.i4.5
0x17d12  callvirt instance class [mscorlib]System.Reflection.Emit.ILGenerator [mscorlib]System.Reflection.Emit.DynamicMethod::GetILGenerator(int32)
0x17d17  stloc.s  4
0x17d19  ldloc.s  4
0x17d1b  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_0
0x17d20  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17d25  ldloc.s  4
0x17d27  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_1
0x17d2c  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17d31  ldloc.s  4
0x17d33  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_2
0x17d38  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17d3d  ldloc.s  4
0x17d3f  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Call
0x17d44  ldloc.2
0x17d45  ldnull
0x17d46  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::EmitCall(valuetype [mscorlib]System.Reflection.Emit.OpCode, class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Type[])
0x17d4b  ldloc.s  4
0x17d4d  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ret
0x17d52  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17d57  ldloc.3
0x17d58  ldtoken  CreateDelegate1Delegate
0x17d5d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d62  callvirt instance class [mscorlib]System.Delegate [mscorlib]System.Reflection.MethodInfo::CreateDelegate(class [mscorlib]System.Type)
0x17d67  castclass CreateDelegate1Delegate
0x17d6c  stsfld   class CreateDelegate1Delegate System.Xaml.Schema.SafeReflectionInvoker::s_CreateDelegate1
0x17d71  ldc.i4.3
0x17d72  newarr   [mscorlib]System.Type
0x17d77  dup
0x17d78  ldc.i4.0
0x17d79  ldtoken  [mscorlib]System.Type
0x17d7e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d83  stelem.ref
0x17d84  dup
0x17d85  ldc.i4.1
0x17d86  ldtoken  [mscorlib]System.Object
0x17d8b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d90  stelem.ref
0x17d91  dup
0x17d92  ldc.i4.2
0x17d93  ldtoken  [mscorlib]System.String
0x17d98  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17d9d  stelem.ref
0x17d9e  stloc.0
0x17d9f  ldtoken  [mscorlib]System.Delegate
0x17da4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17da9  ldstr    aCreatedelegate// "CreateDelegate"
0x17dae  ldloc.0
0x17daf  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x17db4  stloc.2
0x17db5  ldstr    aCreatedelegate// "CreateDelegate"
0x17dba  ldtoken  [mscorlib]System.Delegate
0x17dbf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17dc4  ldloc.0
0x17dc5  newobj   instance void [mscorlib]System.Reflection.Emit.DynamicMethod::.ctor(string, class [mscorlib]System.Type, class [mscorlib]System.Type[])
0x17dca  stloc.3
0x17dcb  ldloc.3
0x17dcc  ldc.i4.1
0x17dcd  ldc.i4.1
0x17dce  ldstr    aDelegatetype// "delegateType"
0x17dd3  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17dd8  pop
0x17dd9  ldloc.3
0x17dda  ldc.i4.2
0x17ddb  ldc.i4.1
0x17ddc  ldstr    aTarget// "target"
0x17de1  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17de6  pop
0x17de7  ldloc.3
0x17de8  ldc.i4.3
0x17de9  ldc.i4.1
0x17dea  ldstr    aMethodname// "methodName"
0x17def  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17df4  pop
0x17df5  ldloc.3
0x17df6  ldc.i4.5
0x17df7  callvirt instance class [mscorlib]System.Reflection.Emit.ILGenerator [mscorlib]System.Reflection.Emit.DynamicMethod::GetILGenerator(int32)
0x17dfc  stloc.s  4
0x17dfe  ldloc.s  4
0x17e00  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_0
0x17e05  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17e0a  ldloc.s  4
0x17e0c  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_1
0x17e11  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17e16  ldloc.s  4
0x17e18  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_2
0x17e1d  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17e22  ldloc.s  4
0x17e24  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Call
0x17e29  ldloc.2
0x17e2a  ldnull
0x17e2b  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::EmitCall(valuetype [mscorlib]System.Reflection.Emit.OpCode, class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Type[])
0x17e30  ldloc.s  4
0x17e32  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ret
0x17e37  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17e3c  ldloc.3
0x17e3d  ldtoken  CreateDelegate2Delegate
0x17e42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e47  callvirt instance class [mscorlib]System.Delegate [mscorlib]System.Reflection.MethodInfo::CreateDelegate(class [mscorlib]System.Type)
0x17e4c  castclass CreateDelegate2Delegate
0x17e51  stsfld   class CreateDelegate2Delegate System.Xaml.Schema.SafeReflectionInvoker::s_CreateDelegate2
0x17e56  ldc.i4.2
0x17e57  newarr   [mscorlib]System.Type
0x17e5c  dup
0x17e5d  ldc.i4.0
0x17e5e  ldtoken  [mscorlib]System.Type
0x17e63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e68  stelem.ref
0x17e69  dup
0x17e6a  ldc.i4.1
0x17e6b  ldtoken  object[]
0x17e70  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e75  stelem.ref
0x17e76  stloc.0
0x17e77  ldtoken  [mscorlib]System.Activator
0x17e7c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e81  ldstr    aCreateinstance// "CreateInstance"
0x17e86  ldloc.0
0x17e87  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x17e8c  stloc.2
0x17e8d  ldstr    aCreateinstance// "CreateInstance"
0x17e92  ldtoken  [mscorlib]System.Object
0x17e97  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17e9c  ldloc.0
0x17e9d  newobj   instance void [mscorlib]System.Reflection.Emit.DynamicMethod::.ctor(string, class [mscorlib]System.Type, class [mscorlib]System.Type[])
0x17ea2  stloc.3
0x17ea3  ldloc.3
0x17ea4  ldc.i4.1
0x17ea5  ldc.i4.1
0x17ea6  ldstr    aType// "type"
0x17eab  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17eb0  pop
0x17eb1  ldloc.3
0x17eb2  ldc.i4.2
0x17eb3  ldc.i4.1
0x17eb4  ldstr    aArguments_0// "arguments"
0x17eb9  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17ebe  pop
0x17ebf  ldloc.3
0x17ec0  ldc.i4.4
0x17ec1  callvirt instance class [mscorlib]System.Reflection.Emit.ILGenerator [mscorlib]System.Reflection.Emit.DynamicMethod::GetILGenerator(int32)
0x17ec6  stloc.s  4
0x17ec8  ldloc.s  4
0x17eca  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_0
0x17ecf  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17ed4  ldloc.s  4
0x17ed6  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_1
0x17edb  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17ee0  ldloc.s  4
0x17ee2  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Call
0x17ee7  ldloc.2
0x17ee8  ldnull
0x17ee9  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::EmitCall(valuetype [mscorlib]System.Reflection.Emit.OpCode, class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Type[])
0x17eee  ldloc.s  4
0x17ef0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ret
0x17ef5  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17efa  ldloc.3
0x17efb  ldtoken  CreateInstanceDelegate
0x17f00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f05  callvirt instance class [mscorlib]System.Delegate [mscorlib]System.Reflection.MethodInfo::CreateDelegate(class [mscorlib]System.Type)
0x17f0a  castclass CreateInstanceDelegate
0x17f0f  stsfld   class CreateInstanceDelegate System.Xaml.Schema.SafeReflectionInvoker::s_CreateInstance
0x17f14  ldc.i4.2
0x17f15  newarr   [mscorlib]System.Type
0x17f1a  dup
0x17f1b  ldc.i4.0
0x17f1c  ldtoken  [mscorlib]System.Object
0x17f21  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f26  stelem.ref
0x17f27  dup
0x17f28  ldc.i4.1
0x17f29  ldtoken  object[]
0x17f2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f33  stelem.ref
0x17f34  stloc.0
0x17f35  ldc.i4.3
0x17f36  newarr   [mscorlib]System.Type
0x17f3b  dup
0x17f3c  ldc.i4.0
0x17f3d  ldtoken  [mscorlib]System.Reflection.MethodInfo
0x17f42  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f47  stelem.ref
0x17f48  dup
0x17f49  ldc.i4.1
0x17f4a  ldtoken  [mscorlib]System.Object
0x17f4f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f54  stelem.ref
0x17f55  dup
0x17f56  ldc.i4.2
0x17f57  ldtoken  object[]
0x17f5c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f61  stelem.ref
0x17f62  stloc.1
0x17f63  ldtoken  [mscorlib]System.Reflection.MethodInfo
0x17f68  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f6d  ldstr    aInvoke// "Invoke"
0x17f72  ldloc.0
0x17f73  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, class [mscorlib]System.Type[])
0x17f78  stloc.2
0x17f79  ldstr    aInvokemethod// "InvokeMethod"
0x17f7e  ldtoken  [mscorlib]System.Object
0x17f83  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x17f88  ldloc.1
0x17f89  newobj   instance void [mscorlib]System.Reflection.Emit.DynamicMethod::.ctor(string, class [mscorlib]System.Type, class [mscorlib]System.Type[])
0x17f8e  stloc.3
0x17f8f  ldloc.3
0x17f90  ldc.i4.1
0x17f91  ldc.i4.1
0x17f92  ldstr    aMethod// "method"
0x17f97  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17f9c  pop
0x17f9d  ldloc.3
0x17f9e  ldc.i4.2
0x17f9f  ldc.i4.1
0x17fa0  ldstr    aInstance// "instance"
0x17fa5  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17faa  pop
0x17fab  ldloc.3
0x17fac  ldc.i4.3
0x17fad  ldc.i4.1
0x17fae  ldstr    aArgs// "args"
0x17fb3  callvirt instance class [mscorlib]System.Reflection.Emit.ParameterBuilder [mscorlib]System.Reflection.Emit.DynamicMethod::DefineParameter(int32, valuetype [mscorlib]System.Reflection.ParameterAttributes, string)
0x17fb8  pop
0x17fb9  ldloc.3
0x17fba  ldc.i4.5
0x17fbb  callvirt instance class [mscorlib]System.Reflection.Emit.ILGenerator [mscorlib]System.Reflection.Emit.DynamicMethod::GetILGenerator(int32)
0x17fc0  stloc.s  4
0x17fc2  ldloc.s  4
0x17fc4  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_0
0x17fc9  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17fce  ldloc.s  4
0x17fd0  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_1
0x17fd5  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17fda  ldloc.s  4
0x17fdc  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ldarg_2
0x17fe1  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x17fe6  ldloc.s  4
0x17fe8  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Callvirt
0x17fed  ldloc.2
0x17fee  ldnull
0x17fef  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::EmitCall(valuetype [mscorlib]System.Reflection.Emit.OpCode, class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Type[])
0x17ff4  ldloc.s  4
0x17ff6  ldsfld   valuetype [mscorlib]System.Reflection.Emit.OpCode [mscorlib]System.Reflection.Emit.OpCodes::Ret
0x17ffb  callvirt instance void [mscorlib]System.Reflection.Emit.ILGenerator::Emit(valuetype [mscorlib]System.Reflection.Emit.OpCode)
0x18000  ldloc.3
0x18001  ldtoken  InvokeMethodDelegate
0x18006  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1800b  callvirt instance class [mscorlib]System.Delegate [mscorlib]System.Reflection.MethodInfo::CreateDelegate(class [mscorlib]System.Type)
  ... truncated ...
```
