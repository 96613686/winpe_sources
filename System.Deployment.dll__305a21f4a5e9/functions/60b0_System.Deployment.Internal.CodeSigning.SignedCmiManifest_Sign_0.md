# System.Deployment.Internal.CodeSigning.SignedCmiManifest::Sign_0

- ea: `0x60b0`
- end: `0x6143`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::Sign_0`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x60a0`

## callees

- `0x60b0`
- `0x6580`
- `0x6a80`
- `0x6ba0`
- `0x6bf0`
- `0x6d60`
- `0x6e00`
- `0x6f50`
- `0x71d0`
- `0x74a0`
- `0x74b0`
- `0x7550`

## pseudocode

```c

```

## disassembly

```asm
0x60b0  ldarg.0
0x60b1  ldnull
0x60b2  stfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_strongNameSignerInfo
0x60b7  ldarg.0
0x60b8  ldnull
0x60b9  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_authenticodeSignerInfo
0x60be  ldarg.1
0x60bf  brfalse.s loc_60C9
0x60c1  ldarg.1
0x60c2  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_StrongNameKey()
0x60c7  brtrue.s loc_60D4
0x60c9  ldstr    aSigner// "signer"
0x60ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x60d3  throw
0x60d4  ldarg.0
0x60d5  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x60da  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest::RemoveExistingSignature(class [System.Xml]System.Xml.XmlDocument manifestDom)
0x60df  ldarg.1
0x60e0  callvirt instance valuetype System.Deployment.Internal.CodeSigning.CmiManifestSignerFlag System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Flag()
0x60e5  ldc.i4.1
0x60e6  and
0x60e7  brtrue.s loc_60FA
0x60e9  ldarg.0
0x60ea  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x60ef  ldarg.1
0x60f0  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_StrongNameKey()
0x60f5  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest::ReplacePublicKeyToken(class [System.Xml]System.Xml.XmlDocument manifestDom, class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm snKey)
0x60fa  ldnull
0x60fb  stloc.0
0x60fc  ldarg.1
0x60fd  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Certificate()
0x6102  brfalse.s loc_6135
0x6104  ldarg.0
0x6105  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x610a  ldarg.1
0x610b  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Certificate()
0x6110  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest::InsertPublisherIdentity(class [System.Xml]System.Xml.XmlDocument manifestDom, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signerCert)
0x6115  ldarg.1
0x6116  ldarg.0
0x6117  call     instance class [System.Xml]System.Xml.XmlElement System.Deployment.Internal.CodeSigning.SignedCmiManifest::ExtractPrincipalFromManifest()
0x611c  ldarg.0
0x611d  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6122  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest::ComputeHashFromManifest(class [System.Xml]System.Xml.XmlDocument manifestDom)
0x6127  call     class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::CreateLicenseDom(class System.Deployment.Internal.CodeSigning.CmiManifestSigner signer, class [System.Xml]System.Xml.XmlElement principal, unsigned int8[] hash)
0x612c  stloc.0
0x612d  ldloc.0
0x612e  ldarg.1
0x612f  ldarg.2
0x6130  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest::AuthenticodeSignLicenseDom(class [System.Xml]System.Xml.XmlDocument licenseDom, class System.Deployment.Internal.CodeSigning.CmiManifestSigner signer, string timeStampUrl)
0x6135  ldarg.0
0x6136  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x613b  ldloc.0
0x613c  ldarg.1
0x613d  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest::StrongNameSignManifestDom(class [System.Xml]System.Xml.XmlDocument manifestDom, class [System.Xml]System.Xml.XmlDocument licenseDom, class System.Deployment.Internal.CodeSigning.CmiManifestSigner signer)
0x6142  ret
```
