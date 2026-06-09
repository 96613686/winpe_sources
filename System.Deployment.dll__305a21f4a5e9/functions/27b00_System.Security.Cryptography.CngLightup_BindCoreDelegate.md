# System.Security.Cryptography.CngLightup::BindCoreDelegate

- ea: `0x27b00`
- end: `0x27b79`
- name: `System.Security.Cryptography.CngLightup::BindCoreDelegate`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x27b00`
- `0x27bd0`

## string_xrefs

- `0x27b00`: `System.Security.Cryptography.X509Certificates.`
- `0x27b06`: `CertificateExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x27b00  ldstr    aSystemSecurity_4// "System.Security.Cryptography.X509Certif"...
0x27b05  ldarg.0
0x27b06  ldstr    aCertificateext// "CertificateExtensions"
0x27b0b  call     string [mscorlib]System.String::Concat(string, string, string)
0x27b10  stloc.0
0x27b11  ldloc.0
0x27b12  ldc.i4.0
0x27b13  call     class [mscorlib]System.Type System.Security.Cryptography.CngLightup::GetSystemCoreType(string namespaceQualifiedTypeName, [opt] bool throwOnError)
0x27b18  stloc.1
0x27b19  ldloc.1
0x27b1a  ldnull
0x27b1b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x27b20  brfalse.s loc_27B24
0x27b22  ldnull
0x27b23  ret
0x27b24  ldstr    aGet// "Get"
0x27b29  ldarg.0
0x27b2a  ldarg.1
0x27b2b  brtrue.s loc_27B34
0x27b2d  ldstr    aPrivate// "Private"
0x27b32  br.s     loc_27B39
0x27b34  ldstr    aPublic// "Public"
0x27b39  ldstr    aKey_0// "Key"
0x27b3e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x27b43  stloc.2
0x27b44  ldloc.1
0x27b45  ldloc.2
0x27b46  ldc.i4.s 0x18
0x27b48  ldnull
0x27b49  ldc.i4.1
0x27b4a  newarr   [mscorlib]System.Type
0x27b4f  dup
0x27b50  ldc.i4.0
0x27b51  ldtoken  [System]System.Security.Cryptography.X509Certificates.X509Certificate2
0x27b56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27b5b  stelem.ref
0x27b5c  ldnull
0x27b5d  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, class [mscorlib]System.Type[], valuetype [mscorlib]System.Reflection.ParameterModifier[])
0x27b62  stloc.3
0x27b63  ldloc.3
0x27b64  ldtoken  class [mscorlib]System.Func`2<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2, mvar<u1>>
0x27b69  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27b6e  callvirt instance class [mscorlib]System.Delegate [mscorlib]System.Reflection.MethodInfo::CreateDelegate(class [mscorlib]System.Type)
0x27b73  castclass class [mscorlib]System.Func`2<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2, mvar<u1>>
0x27b78  ret
```
