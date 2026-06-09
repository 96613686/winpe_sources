# System.Security.Cryptography.CngLightup::DetectRsaCngSupport

- ea: `0x27a30`
- end: `0x27aa1`
- name: `System.Security.Cryptography.CngLightup::DetectRsaCngSupport`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x27a30`
- `0x27bd0`

## string_xrefs

- `0x27a30`: `System.Security.Cryptography.RSACng`
- `0x27a47`: `System.Security.Cryptography.DSACng`

## pseudocode

```c

```

## disassembly

```asm
0x27a30  ldstr    aSystemSecurity_2// "System.Security.Cryptography.RSACng"
0x27a35  ldc.i4.0
0x27a36  call     class [mscorlib]System.Type System.Security.Cryptography.CngLightup::GetSystemCoreType(string namespaceQualifiedTypeName, [opt] bool throwOnError)
0x27a3b  stloc.0
0x27a3c  ldloc.0
0x27a3d  ldnull
0x27a3e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x27a43  brfalse.s loc_27A47
0x27a45  ldc.i4.0
0x27a46  ret
0x27a47  ldstr    aSystemSecurity_3// "System.Security.Cryptography.DSACng"
0x27a4c  ldc.i4.0
0x27a4d  call     class [mscorlib]System.Type System.Security.Cryptography.CngLightup::GetSystemCoreType(string namespaceQualifiedTypeName, [opt] bool throwOnError)
0x27a52  stloc.1
0x27a53  ldloc.1
0x27a54  ldnull
0x27a55  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x27a5a  brfalse.s loc_27A5E
0x27a5c  ldc.i4.0
0x27a5d  ret
0x27a5e  ldc.i4.2
0x27a5f  newarr   [mscorlib]System.Type
0x27a64  dup
0x27a65  ldc.i4.0
0x27a66  ldtoken  unsigned int8[]
0x27a6b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27a70  stelem.ref
0x27a71  dup
0x27a72  ldc.i4.1
0x27a73  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_hashAlgorithmNameType
0x27a78  stelem.ref
0x27a79  stloc.2
0x27a7a  ldtoken  [mscorlib]System.Security.Cryptography.DSA
0x27a7f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27a84  ldstr    aSigndata// "SignData"
0x27a89  ldc.i4.s 0x14
0x27a8b  ldnull
0x27a8c  ldloc.2
0x27a8d  ldnull
0x27a8e  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x27a93  stloc.3
0x27a94  ldloc.3
0x27a95  ldnull
0x27a96  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x27a9b  brfalse.s loc_27A9F
0x27a9d  ldc.i4.0
0x27a9e  ret
0x27a9f  ldc.i4.1
0x27aa0  ret
```
