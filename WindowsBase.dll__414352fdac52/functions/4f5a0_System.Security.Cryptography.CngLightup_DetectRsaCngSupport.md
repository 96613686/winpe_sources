# System.Security.Cryptography.CngLightup::DetectRsaCngSupport

- ea: `0x4f5a0`
- end: `0x4f611`
- name: `System.Security.Cryptography.CngLightup::DetectRsaCngSupport`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x4f5a0`
- `0x4f740`

## string_xrefs

- `0x4f5a0`: `System.Security.Cryptography.RSACng`
- `0x4f5b7`: `System.Security.Cryptography.DSACng`

## pseudocode

```c

```

## disassembly

```asm
0x4f5a0  ldstr    aSystemSecurity// "System.Security.Cryptography.RSACng"
0x4f5a5  ldc.i4.0
0x4f5a6  call     class [mscorlib]System.Type System.Security.Cryptography.CngLightup::GetSystemCoreType(string namespaceQualifiedTypeName, [opt] bool throwOnError)
0x4f5ab  stloc.0
0x4f5ac  ldloc.0
0x4f5ad  ldnull
0x4f5ae  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f5b3  brfalse.s loc_4F5B7
0x4f5b5  ldc.i4.0
0x4f5b6  ret
0x4f5b7  ldstr    aSystemSecurity_0// "System.Security.Cryptography.DSACng"
0x4f5bc  ldc.i4.0
0x4f5bd  call     class [mscorlib]System.Type System.Security.Cryptography.CngLightup::GetSystemCoreType(string namespaceQualifiedTypeName, [opt] bool throwOnError)
0x4f5c2  stloc.1
0x4f5c3  ldloc.1
0x4f5c4  ldnull
0x4f5c5  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f5ca  brfalse.s loc_4F5CE
0x4f5cc  ldc.i4.0
0x4f5cd  ret
0x4f5ce  ldc.i4.2
0x4f5cf  newarr   [mscorlib]System.Type
0x4f5d4  dup
0x4f5d5  ldc.i4.0
0x4f5d6  ldtoken  unsigned int8[]
0x4f5db  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f5e0  stelem.ref
0x4f5e1  dup
0x4f5e2  ldc.i4.1
0x4f5e3  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_hashAlgorithmNameType
0x4f5e8  stelem.ref
0x4f5e9  stloc.2
0x4f5ea  ldtoken  [mscorlib]System.Security.Cryptography.DSA
0x4f5ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f5f4  ldstr    aSigndata// "SignData"
0x4f5f9  ldc.i4.s 0x14
0x4f5fb  ldnull
0x4f5fc  ldloc.2
0x4f5fd  ldnull
0x4f5fe  call     instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x4f603  stloc.3
0x4f604  ldloc.3
0x4f605  ldnull
0x4f606  call     bool [mscorlib]System.Reflection.MethodInfo::op_Equality(class [mscorlib]System.Reflection.MethodInfo, class [mscorlib]System.Reflection.MethodInfo)
0x4f60b  brfalse.s loc_4F60F
0x4f60d  ldc.i4.0
0x4f60e  ret
0x4f60f  ldc.i4.1
0x4f610  ret
```
