# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::Sign_0

- ea: `0x7a80`
- end: `0x7b33`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::Sign_0`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x7a70`

## callees

- `0x7a80`
- `0x8f90`
- `0x9490`
- `0x95b0`
- `0x9670`
- `0x9820`
- `0x9900`
- `0x9a50`
- `0x9ea0`
- `0xa230`
- `0xa240`
- `0xa2e0`

## pseudocode

```c

```

## disassembly

```asm
0x7a80  ldarg.0
0x7a81  ldnull
0x7a82  stfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_strongNameSignerInfo
0x7a87  ldarg.0
0x7a88  ldnull
0x7a89  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7a8e  ldarg.1
0x7a8f  brfalse.s loc_7A99
0x7a91  ldarg.1
0x7a92  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_StrongNameKey()
0x7a97  brtrue.s loc_7AA4
0x7a99  ldstr    aSigner// "signer"
0x7a9e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7aa3  throw
0x7aa4  ldarg.0
0x7aa5  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7aaa  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::RemoveExistingSignature(class [System.Xml]System.Xml.XmlDocument manifestDom)
0x7aaf  ldarg.1
0x7ab0  callvirt instance valuetype System.Deployment.Internal.CodeSigning.CmiManifestSignerFlag System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_Flag()
0x7ab5  ldc.i4.1
0x7ab6  and
0x7ab7  brtrue.s loc_7AD0
0x7ab9  ldarg.0
0x7aba  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7abf  ldarg.1
0x7ac0  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_StrongNameKey()
0x7ac5  ldarg.0
0x7ac6  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7acb  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ReplacePublicKeyToken(class [System.Xml]System.Xml.XmlDocument manifestDom, class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm snKey, bool useSha256)
0x7ad0  ldnull
0x7ad1  stloc.0
0x7ad2  ldarg.1
0x7ad3  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_Certificate()
0x7ad8  brfalse.s loc_7B1F
0x7ada  ldarg.0
0x7adb  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7ae0  ldarg.1
0x7ae1  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_Certificate()
0x7ae6  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::InsertPublisherIdentity(class [System.Xml]System.Xml.XmlDocument manifestDom, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signerCert)
0x7aeb  ldarg.0
0x7aec  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7af1  brtrue.s loc_7AF6
0x7af3  ldc.i4.0
0x7af4  br.s     loc_7AF7
0x7af6  ldc.i4.1
0x7af7  stloc.1
0x7af8  ldarg.1
0x7af9  ldarg.0
0x7afa  call     instance class [System.Xml]System.Xml.XmlElement System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ExtractPrincipalFromManifest()
0x7aff  ldarg.0
0x7b00  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7b05  ldloc.1
0x7b06  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ComputeHashFromManifest(class [System.Xml]System.Xml.XmlDocument manifestDom, valuetype System.Deployment.Internal.CodeSigning.SupportedHashAlgorithm supportedHashAlgorithm)
0x7b0b  call     class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::CreateLicenseDom(class System.Deployment.Internal.CodeSigning.CmiManifestSigner2 signer, class [System.Xml]System.Xml.XmlElement principal, unsigned int8[] hash)
0x7b10  stloc.0
0x7b11  ldloc.0
0x7b12  ldarg.1
0x7b13  ldarg.2
0x7b14  ldarg.0
0x7b15  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7b1a  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::AuthenticodeSignLicenseDom(class [System.Xml]System.Xml.XmlDocument licenseDom, class System.Deployment.Internal.CodeSigning.CmiManifestSigner2 signer, string timeStampUrl, bool useSha256)
0x7b1f  ldarg.0
0x7b20  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7b25  ldloc.0
0x7b26  ldarg.1
0x7b27  ldarg.0
0x7b28  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7b2d  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::StrongNameSignManifestDom(class [System.Xml]System.Xml.XmlDocument manifestDom, class [System.Xml]System.Xml.XmlDocument licenseDom, class System.Deployment.Internal.CodeSigning.CmiManifestSigner2 signer, bool useSha256)
0x7b32  ret
```
