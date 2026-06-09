# System.Deployment.Internal.CodeSigning.ManifestSignedXml2::init

- ea: `0x7930`
- end: `0x79df`
- name: `System.Deployment.Internal.CodeSigning.ManifestSignedXml2::init`
- size: `175`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x78e0`
- `0x78f0`
- `0x7900`
- `0x7910`

## string_xrefs

- `0x7942`: `http://www.w3.org/2000/09/xmldsig#rsa-sha512`
- `0x795f`: `http://www.w3.org/2000/09/xmldsig#sha512`
- `0x797c`: `http://www.w3.org/2000/09/xmldsig#rsa-sha384`
- `0x7999`: `http://www.w3.org/2000/09/xmldsig#sha384`
- `0x79b6`: `http://www.w3.org/2000/09/xmldsig#rsa-sha256`
- `0x79d3`: `http://www.w3.org/2000/09/xmldsig#sha256`

## pseudocode

```c

```

## disassembly

```asm
0x7930  ldtoken  System.Deployment.Internal.CodeSigning.RSAPKCS1SHA512SignatureDescription
0x7935  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x793a  ldc.i4.1
0x793b  newarr   [mscorlib]System.String
0x7940  dup
0x7941  ldc.i4.0
0x7942  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x7947  stelem.ref
0x7948  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x794d  ldtoken  [System.Core]System.Security.Cryptography.SHA512Cng
0x7952  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7957  ldc.i4.1
0x7958  newarr   [mscorlib]System.String
0x795d  dup
0x795e  ldc.i4.0
0x795f  ldstr    aHttpWwwW3Org20_3// "http://www.w3.org/2000/09/xmldsig#sha51"...
0x7964  stelem.ref
0x7965  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x796a  ldtoken  System.Deployment.Internal.CodeSigning.RSAPKCS1SHA384SignatureDescription
0x796f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7974  ldc.i4.1
0x7975  newarr   [mscorlib]System.String
0x797a  dup
0x797b  ldc.i4.0
0x797c  ldstr    aHttpWwwW3Org20_4// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x7981  stelem.ref
0x7982  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x7987  ldtoken  [System.Core]System.Security.Cryptography.SHA384Cng
0x798c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7991  ldc.i4.1
0x7992  newarr   [mscorlib]System.String
0x7997  dup
0x7998  ldc.i4.0
0x7999  ldstr    aHttpWwwW3Org20_5// "http://www.w3.org/2000/09/xmldsig#sha38"...
0x799e  stelem.ref
0x799f  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x79a4  ldtoken  System.Deployment.Internal.CodeSigning.RSAPKCS1SHA256SignatureDescription
0x79a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x79ae  ldc.i4.1
0x79af  newarr   [mscorlib]System.String
0x79b4  dup
0x79b5  ldc.i4.0
0x79b6  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x79bb  stelem.ref
0x79bc  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x79c1  ldtoken  [System.Core]System.Security.Cryptography.SHA256Cng
0x79c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x79cb  ldc.i4.1
0x79cc  newarr   [mscorlib]System.String
0x79d1  dup
0x79d2  ldc.i4.0
0x79d3  ldstr    aHttpWwwW3Org20_7// "http://www.w3.org/2000/09/xmldsig#sha25"...
0x79d8  stelem.ref
0x79d9  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x79de  ret
```
