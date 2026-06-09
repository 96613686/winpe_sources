# System.Security.Cryptography.CngLightup::.cctor

- ea: `0x4f760`
- end: `0x4f858`
- name: `System.Security.Cryptography.CngLightup::.cctor`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4f760`

## string_xrefs

- `0x4f76f`: `System.Security.Cryptography.HashAlgorithmName`
- `0x4f78e`: `System.Security.Cryptography.RSASignaturePadding`
- `0x4f7ad`: `System.Security.Cryptography.RSAEncryptionPadding`

## pseudocode

```c

```

## disassembly

```asm
0x4f760  ldtoken  [mscorlib]System.Object
0x4f765  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f76a  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x4f76f  ldstr    aSystemSecurity_2// "System.Security.Cryptography.HashAlgori"...
0x4f774  ldc.i4.0
0x4f775  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x4f77a  stsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_hashAlgorithmNameType
0x4f77f  ldtoken  [mscorlib]System.Object
0x4f784  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f789  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x4f78e  ldstr    aSystemSecurity_3// "System.Security.Cryptography.RSASignatu"...
0x4f793  ldc.i4.0
0x4f794  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x4f799  stsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaSignaturePaddingType
0x4f79e  ldtoken  [mscorlib]System.Object
0x4f7a3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f7a8  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x4f7ad  ldstr    aSystemSecurity_4// "System.Security.Cryptography.RSAEncrypt"...
0x4f7b2  ldc.i4.0
0x4f7b3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x4f7b8  stsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x4f7bd  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaSignaturePaddingType
0x4f7c2  ldnull
0x4f7c3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f7c8  brtrue.s loc_4F7E3
0x4f7ca  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaSignaturePaddingType
0x4f7cf  ldstr    aPkcs1// "Pkcs1"
0x4f7d4  ldc.i4.s 0x18
0x4f7d6  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x4f7db  ldnull
0x4f7dc  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x4f7e1  br.s     loc_4F7E4
0x4f7e3  ldnull
0x4f7e4  stsfld   object System.Security.Cryptography.CngLightup::s_pkcs1SignaturePadding
0x4f7e9  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x4f7ee  ldnull
0x4f7ef  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f7f4  brtrue.s loc_4F80F
0x4f7f6  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x4f7fb  ldstr    aPkcs1// "Pkcs1"
0x4f800  ldc.i4.s 0x18
0x4f802  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x4f807  ldnull
0x4f808  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x4f80d  br.s     loc_4F810
0x4f80f  ldnull
0x4f810  stsfld   object System.Security.Cryptography.CngLightup::s_pkcs1EncryptionPadding
0x4f815  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x4f81a  ldnull
0x4f81b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x4f820  brtrue.s loc_4F83B
0x4f822  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x4f827  ldstr    aOaepsha1// "OaepSHA1"
0x4f82c  ldc.i4.s 0x18
0x4f82e  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x4f833  ldnull
0x4f834  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x4f839  br.s     loc_4F83C
0x4f83b  ldnull
0x4f83c  stsfld   object System.Security.Cryptography.CngLightup::s_oaepSha1EncryptionPadding
0x4f841  ldnull
0x4f842  ldftn    bool System.Security.Cryptography.CngLightup::DetectRsaCngSupport()
0x4f848  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x4f84d  newobj   instance void class [mscorlib]System.Lazy`1<bool>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x4f852  stsfld   class [mscorlib]System.Lazy`1<bool> System.Security.Cryptography.CngLightup::s_preferRsaCng
0x4f857  ret
```
