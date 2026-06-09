# System.Security.Cryptography.CngLightup::.cctor

- ea: `0x27bf0`
- end: `0x27ce8`
- name: `System.Security.Cryptography.CngLightup::.cctor`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x27bf0`

## string_xrefs

- `0x27bff`: `System.Security.Cryptography.HashAlgorithmName`
- `0x27c1e`: `System.Security.Cryptography.RSASignaturePadding`
- `0x27c3d`: `System.Security.Cryptography.RSAEncryptionPadding`

## pseudocode

```c

```

## disassembly

```asm
0x27bf0  ldtoken  [mscorlib]System.Object
0x27bf5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27bfa  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x27bff  ldstr    aSystemSecurity_5// "System.Security.Cryptography.HashAlgori"...
0x27c04  ldc.i4.0
0x27c05  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x27c0a  stsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_hashAlgorithmNameType
0x27c0f  ldtoken  [mscorlib]System.Object
0x27c14  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27c19  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x27c1e  ldstr    aSystemSecurity_6// "System.Security.Cryptography.RSASignatu"...
0x27c23  ldc.i4.0
0x27c24  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x27c29  stsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaSignaturePaddingType
0x27c2e  ldtoken  [mscorlib]System.Object
0x27c33  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27c38  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x27c3d  ldstr    aSystemSecurity_7// "System.Security.Cryptography.RSAEncrypt"...
0x27c42  ldc.i4.0
0x27c43  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x27c48  stsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x27c4d  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaSignaturePaddingType
0x27c52  ldnull
0x27c53  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x27c58  brtrue.s loc_27C73
0x27c5a  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaSignaturePaddingType
0x27c5f  ldstr    aPkcs1// "Pkcs1"
0x27c64  ldc.i4.s 0x18
0x27c66  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x27c6b  ldnull
0x27c6c  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x27c71  br.s     loc_27C74
0x27c73  ldnull
0x27c74  stsfld   object System.Security.Cryptography.CngLightup::s_pkcs1SignaturePadding
0x27c79  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x27c7e  ldnull
0x27c7f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x27c84  brtrue.s loc_27C9F
0x27c86  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x27c8b  ldstr    aPkcs1// "Pkcs1"
0x27c90  ldc.i4.s 0x18
0x27c92  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x27c97  ldnull
0x27c98  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x27c9d  br.s     loc_27CA0
0x27c9f  ldnull
0x27ca0  stsfld   object System.Security.Cryptography.CngLightup::s_pkcs1EncryptionPadding
0x27ca5  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x27caa  ldnull
0x27cab  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x27cb0  brtrue.s loc_27CCB
0x27cb2  ldsfld   class [mscorlib]System.Type System.Security.Cryptography.CngLightup::s_rsaEncryptionPaddingType
0x27cb7  ldstr    aOaepsha1// "OaepSHA1"
0x27cbc  ldc.i4.s 0x18
0x27cbe  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x27cc3  ldnull
0x27cc4  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object)
0x27cc9  br.s     loc_27CCC
0x27ccb  ldnull
0x27ccc  stsfld   object System.Security.Cryptography.CngLightup::s_oaepSha1EncryptionPadding
0x27cd1  ldnull
0x27cd2  ldftn    bool System.Security.Cryptography.CngLightup::DetectRsaCngSupport()
0x27cd8  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x27cdd  newobj   instance void class [mscorlib]System.Lazy`1<bool>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x27ce2  stsfld   class [mscorlib]System.Lazy`1<bool> System.Security.Cryptography.CngLightup::s_preferRsaCng
0x27ce7  ret
```
