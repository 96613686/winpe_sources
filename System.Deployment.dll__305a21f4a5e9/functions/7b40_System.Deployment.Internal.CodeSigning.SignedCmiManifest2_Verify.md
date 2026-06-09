# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::Verify

- ea: `0x7b40`
- end: `0x7c5d`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::Verify`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x26a90`

## callees

- `0x75a0`
- `0x75d0`
- `0x7610`
- `0x7910`
- `0x7b40`
- `0x7c80`
- `0x7e60`
- `0x8470`
- `0x92e0`
- `0xa100`
- `0xa330`

## string_xrefs

- `0x7b65`: `http://www.w3.org/2000/09/xmldsig#`

## pseudocode

```c

```

## disassembly

```asm
0x7b40  ldarg.0
0x7b41  ldnull
0x7b42  stfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_strongNameSignerInfo
0x7b47  ldarg.0
0x7b48  ldnull
0x7b49  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7b4e  ldarg.0
0x7b4f  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7b54  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x7b59  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x7b5e  stloc.0
0x7b5f  ldloc.0
0x7b60  ldstr    aDs// "ds"
0x7b65  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x7b6a  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7b6f  ldarg.0
0x7b70  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7b75  ldstr    aDsSignatureIdS// "//ds:Signature[@Id=\"StrongNameSignatur"...
0x7b7a  ldloc.0
0x7b7b  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x7b80  isinst   [System.Xml]System.Xml.XmlElement
0x7b85  stloc.1
0x7b86  ldloc.1
0x7b87  brtrue.s loc_7B94
0x7b89  ldc.i4   0x800B0100
0x7b8e  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x7b93  throw
0x7b94  ldarg.0
0x7b95  ldloc.1
0x7b96  ldstr    aStrongnamesign// "StrongNameSignature"
0x7b9b  ldloc.0
0x7b9c  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureForm(class [System.Xml]System.Xml.XmlElement signatureNode, string signatureKind, class [System.Xml]System.Xml.XmlNamespaceManager nsm)
0x7ba1  ldarg.0
0x7ba2  call     instance string System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyPublicKeyToken()
0x7ba7  stloc.2
0x7ba8  ldarg.0
0x7ba9  ldc.i4   0x800B010B
0x7bae  ldloc.2
0x7baf  newobj   instance void System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo::.ctor(int32 errorCode, string publicKeyToken)
0x7bb4  stfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_strongNameSignerInfo
0x7bb9  ldarg.0
0x7bba  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7bbf  ldc.i4.1
0x7bc0  newobj   instance void System.Deployment.Internal.CodeSigning.ManifestSignedXml2::.ctor(class [System.Xml]System.Xml.XmlDocument document, bool verify)
0x7bc5  stloc.3
0x7bc6  ldloc.3
0x7bc7  ldloc.1
0x7bc8  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::LoadXml(class [System.Xml]System.Xml.XmlElement)
0x7bcd  ldc.i4.3
0x7bce  stloc.s  4
0x7bd0  ldarg.0
0x7bd1  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7bd6  brfalse.s loc_7BFC
0x7bd8  ldloc.3
0x7bd9  callvirt instance class [System.Security]System.Security.Cryptography.Xml.SignedInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_SignedInfo()
0x7bde  callvirt instance string [System.Security]System.Security.Cryptography.Xml.SignedInfo::get_SignatureMethod()
0x7be3  ldarg.0
0x7be4  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7be9  ldarg.0
0x7bea  ldftn    instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::<Verify>b__12_0()
0x7bf0  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7bf5  call     valuetype System.Deployment.Internal.CodeSigning.SupportedHashAlgorithm System.Deployment.Internal.CodeSigning.ManifestUtilities::GetSupportedHashAlgorithmFromSignatureMethod(string signatureMethodUri, bool useSha256OrHigher, class [mscorlib]System.Action onError)
0x7bfa  stloc.s  4
0x7bfc  ldnull
0x7bfd  stloc.s  5
0x7bff  ldloc.3
0x7c00  ldloca.s 5
0x7c02  callvirt instance bool [System.Security]System.Security.Cryptography.Xml.SignedXml::CheckSignatureReturningKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm&)
0x7c07  stloc.s  6
0x7c09  ldarg.0
0x7c0a  ldfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_strongNameSignerInfo
0x7c0f  ldloc.s  5
0x7c11  callvirt instance void System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo::set_PublicKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm value)
0x7c16  ldloc.s  6
0x7c18  brtrue.s loc_7C35
0x7c1a  ldarg.0
0x7c1b  ldfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_strongNameSignerInfo
0x7c20  ldc.i4   0x80096010
0x7c25  callvirt instance void System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo::set_ErrorCode(int32 value)
0x7c2a  ldc.i4   0x80096010
0x7c2f  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x7c34  throw
0x7c35  ldarg.1
0x7c36  ldc.i4   0x10000
0x7c3b  and
0x7c3c  ldc.i4   0x10000
0x7c41  beq.s    loc_7C5C
0x7c43  ldarg.0
0x7c44  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7c49  brfalse.s loc_7C55
0x7c4b  ldarg.0
0x7c4c  ldarg.1
0x7c4d  ldloc.s  4
0x7c4f  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyLicenseNew(valuetype System.Deployment.Internal.CodeSigning.CmiManifestVerifyFlags verifyFlags, valuetype System.Deployment.Internal.CodeSigning.SupportedHashAlgorithm supportedHashAlgorithm)
0x7c54  ret
0x7c55  ldarg.0
0x7c56  ldarg.1
0x7c57  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyLicense(valuetype System.Deployment.Internal.CodeSigning.CmiManifestVerifyFlags verifyFlags)
0x7c5c  ret
```
