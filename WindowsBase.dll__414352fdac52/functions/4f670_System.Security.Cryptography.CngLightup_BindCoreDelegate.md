# System.Security.Cryptography.CngLightup::BindCoreDelegate

- ea: `0x4f670`
- end: `0x4f6e9`
- name: `System.Security.Cryptography.CngLightup::BindCoreDelegate`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4f670`
- `0x4f740`

## string_xrefs

- `0x4f670`: `System.Security.Cryptography.X509Certificates.`
- `0x4f676`: `CertificateExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x4f670  ldstr    aSystemSecurity_1// "System.Security.Cryptography.X509Certif"...
0x4f675  ldarg.0
0x4f676  ldstr    aCertificateext// "CertificateExtensions"
0x4f67b  call     string [mscorlib]System.String::Concat(string, string, string)
0x4f680  stloc.0
0x4f681  ldloc.0
0x4f682  ldc.i4.0
0x4f683  call     class [mscorlib]System.Type System.Security.Cryptography.CngLightup::GetSystemCoreType(string namespaceQualifiedTypeName, [opt] bool throwOnError)
0x4f688  stloc.1
0x4f689  ldloc.1
0x4f68a  ldnull
0x4f68b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f690  brfalse.s loc_4F694
0x4f692  ldnull
0x4f693  ret
0x4f694  ldstr    aGet// "Get"
0x4f699  ldarg.0
0x4f69a  ldarg.1
0x4f69b  brtrue.s loc_4F6A4
0x4f69d  ldstr    aPrivate// "Private"
0x4f6a2  br.s     loc_4F6A9
0x4f6a4  ldstr    aPublic// "Public"
0x4f6a9  ldstr    aKey_0// "Key"
0x4f6ae  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x4f6b3  stloc.2
0x4f6b4  ldloc.1
0x4f6b5  ldloc.2
0x4f6b6  ldc.i4.s 0x18
0x4f6b8  ldnull
0x4f6b9  ldc.i4.1
0x4f6ba  newarr   [mscorlib]System.Type
0x4f6bf  dup
0x4f6c0  ldc.i4.0
0x4f6c1  ldtoken  [System]System.Security.Cryptography.X509Certificates.X509Certificate2
0x4f6c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f6cb  stelem.ref
0x4f6cc  ldnull
0x4f6cd  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x4f6d2  stloc.3
0x4f6d3  ldloc.3
0x4f6d4  ldtoken  class [mscorlib]System.Func`2<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2, mvar<u1>>
0x4f6d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f6de  callvirt instance class [mscorlib]System.Delegate [mscorlib]System.Reflection.MethodInfo::CreateDelegate(class [mscorlib]System.Type)
0x4f6e3  castclass class [mscorlib]System.Func`2<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2, mvar<u1>>
0x4f6e8  ret
```
