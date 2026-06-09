# System.Deployment.Application.Manifest.AssemblyManifest::ValidateSignature

- ea: `0x25a00`
- end: `0x25b6e`
- name: `System.Deployment.Application.Manifest.AssemblyManifest::ValidateSignature`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10650`
- `0x19e90`

## callees

- `0x6080`
- `0x6150`
- `0xdaa0`
- `0x147a0`
- `0x147b0`
- `0x17cb0`
- `0x17d40`
- `0x23020`
- `0x232e0`
- `0x24970`
- `0x250b0`
- `0x25a00`

## string_xrefs

- `0x25a88`: `http://www.w3.org/2000/09/xmldsig#rsa-sha512`
- `0x25aa5`: `http://www.w3.org/2000/09/xmldsig#sha512`
- `0x25ac2`: `http://www.w3.org/2000/09/xmldsig#rsa-sha384`
- `0x25adf`: `http://www.w3.org/2000/09/xmldsig#sha384`
- `0x25afc`: `http://www.w3.org/2000/09/xmldsig#rsa-sha256`
- `0x25b19`: `http://www.w3.org/2000/09/xmldsig#sha256`
- `0x25a24`: `UnsignedManifest`
- `0x25a3e`: `Manifest is unsigned.`
- `0x25b3b`: `Ex_InvalidXmlSignature`
- `0x25b56`: `Ex_SignedManifestUnhashedComponent`

## pseudocode

```c

```

## disassembly

```asm
0x25a00  ldarg.0
0x25a01  call     instance class System.Deployment.Application.DefinitionIdentity System.Deployment.Application.Manifest.AssemblyManifest::get_Identity()
0x25a06  callvirt instance string System.Deployment.Application.DefinitionIdentity::get_PublicKeyToken()
0x25a0b  ldstr    a00000000000000_0// "0000000000000000"
0x25a10  ldc.i4.4
0x25a11  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x25a16  brfalse.s loc_25A50
0x25a18  call     bool System.Deployment.Application.PolicyKeys::RequireSignedManifests()
0x25a1d  brtrue.s loc_25A50
0x25a1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x25a24  ldstr    aUnsignedmanife// "UnsignedManifest"
0x25a29  call     string System.Deployment.Application.Resources::GetString(string s)
0x25a2e  ldc.i4.0
0x25a2f  newarr   [mscorlib]System.Object
0x25a34  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25a39  call     void System.Deployment.Application.Logger::AddWarningInformation(string message)
0x25a3e  ldstr    aManifestIsUnsi// "Manifest is unsigned."
0x25a43  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x25a48  ldarg.0
0x25a49  ldc.i4.0
0x25a4a  stfld    bool System.Deployment.Application.Manifest.AssemblyManifest::_signed
0x25a4f  ret
0x25a50  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x25a55  stloc.0
0x25a56  ldloc.0
0x25a57  ldc.i4.1
0x25a58  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_PreserveWhitespace(bool)
0x25a5d  ldarg.1
0x25a5e  brfalse.s loc_25A69
0x25a60  ldloc.0
0x25a61  ldarg.1
0x25a62  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [mscorlib]System.IO.Stream)
0x25a67  br.s     loc_25A75
0x25a69  ldloc.0
0x25a6a  ldarg.0
0x25a6b  ldfld    string System.Deployment.Application.Manifest.AssemblyManifest::_rawXmlFilePath
0x25a70  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(string)
0x25a75  nop
0x25a76  ldtoken  System.Deployment.Internal.CodeSigning.RSAPKCS1SHA512SignatureDescription
0x25a7b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25a80  ldc.i4.1
0x25a81  newarr   [mscorlib]System.String
0x25a86  dup
0x25a87  ldc.i4.0
0x25a88  ldstr    aHttpWwwW3Org20_2// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x25a8d  stelem.ref
0x25a8e  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x25a93  ldtoken  [System.Core]System.Security.Cryptography.SHA512Cng
0x25a98  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25a9d  ldc.i4.1
0x25a9e  newarr   [mscorlib]System.String
0x25aa3  dup
0x25aa4  ldc.i4.0
0x25aa5  ldstr    aHttpWwwW3Org20_3// "http://www.w3.org/2000/09/xmldsig#sha51"...
0x25aaa  stelem.ref
0x25aab  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x25ab0  ldtoken  System.Deployment.Internal.CodeSigning.RSAPKCS1SHA384SignatureDescription
0x25ab5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25aba  ldc.i4.1
0x25abb  newarr   [mscorlib]System.String
0x25ac0  dup
0x25ac1  ldc.i4.0
0x25ac2  ldstr    aHttpWwwW3Org20_4// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x25ac7  stelem.ref
0x25ac8  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x25acd  ldtoken  [System.Core]System.Security.Cryptography.SHA384Cng
0x25ad2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25ad7  ldc.i4.1
0x25ad8  newarr   [mscorlib]System.String
0x25add  dup
0x25ade  ldc.i4.0
0x25adf  ldstr    aHttpWwwW3Org20_5// "http://www.w3.org/2000/09/xmldsig#sha38"...
0x25ae4  stelem.ref
0x25ae5  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x25aea  ldtoken  System.Deployment.Internal.CodeSigning.RSAPKCS1SHA256SignatureDescription
0x25aef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25af4  ldc.i4.1
0x25af5  newarr   [mscorlib]System.String
0x25afa  dup
0x25afb  ldc.i4.0
0x25afc  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x25b01  stelem.ref
0x25b02  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x25b07  ldtoken  [System.Core]System.Security.Cryptography.SHA256Cng
0x25b0c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25b11  ldc.i4.1
0x25b12  newarr   [mscorlib]System.String
0x25b17  dup
0x25b18  ldc.i4.0
0x25b19  ldstr    aHttpWwwW3Org20_7// "http://www.w3.org/2000/09/xmldsig#sha25"...
0x25b1e  stelem.ref
0x25b1f  call     void [mscorlib]System.Security.Cryptography.CryptoConfig::AddAlgorithm(class [mscorlib]System.Type, string[])
0x25b24  ldloc.0
0x25b25  newobj   instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest::.ctor(class [System.Xml]System.Xml.XmlDocument manifestDom)
0x25b2a  stloc.1
0x25b2b  ldloc.1
0x25b2c  ldc.i4   0x10000
0x25b31  callvirt instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest::Verify(valuetype System.Deployment.Internal.CodeSigning.CmiManifestVerifyFlags verifyFlags)
0x25b36  leave.s  loc_25B4C
0x25b38  stloc.2
0x25b39  ldc.i4.s 0x1A
0x25b3b  ldstr    aExInvalidxmlsi// "Ex_InvalidXmlSignature"
0x25b40  call     string System.Deployment.Application.Resources::GetString(string s)
0x25b45  ldloc.2
0x25b46  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message, class [mscorlib]System.Exception innerException)
0x25b4b  throw
0x25b4c  ldarg.0
0x25b4d  call     instance bool System.Deployment.Application.Manifest.AssemblyManifest::get_RequiredHashMissing()
0x25b52  brfalse.s loc_25B66
0x25b54  ldc.i4.s 0x1A
0x25b56  ldstr    aExSignedmanife// "Ex_SignedManifestUnhashedComponent"
0x25b5b  call     string System.Deployment.Application.Resources::GetString(string s)
0x25b60  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x25b65  throw
0x25b66  ldarg.0
0x25b67  ldc.i4.1
0x25b68  stfld    bool System.Deployment.Application.Manifest.AssemblyManifest::_signed
0x25b6d  ret
```
