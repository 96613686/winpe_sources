# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::AuthenticodeSignLicenseDom

- ea: `0x9a50`
- end: `0x9bad`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::AuthenticodeSignLicenseDom`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7a80`

## callees

- `0x7900`
- `0x9a50`
- `0x9d20`
- `0xa100`
- `0xa220`
- `0xa240`
- `0xa2a0`
- `0x27460`

## string_xrefs

- `0x9a79`: `http://www.w3.org/2001/10/xml-exc-c14n#`
- `0x9b86`: `<msrel:RelData xmlns:msrel="http://schemas.microsoft.com/windows/rel/2005/reldata">`
- `0x9a91`: `http://www.w3.org/2000/09/xmldsig#rsa-sha256`
- `0x9ae2`: `http://www.w3.org/2000/09/xmldsig#sha256`

## pseudocode

```c

```

## disassembly

```asm
0x9a50  ldarg.1
0x9a51  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_Certificate()
0x9a56  call     class [mscorlib]System.Security.Cryptography.RSA System.Security.Cryptography.CngLightup::GetRSAPrivateKey(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 cert)
0x9a5b  stloc.0
0x9a5c  ldloc.0
0x9a5d  brtrue.s loc_9A65
0x9a5f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x9a64  throw
0x9a65  ldarg.0
0x9a66  newobj   instance void System.Deployment.Internal.CodeSigning.ManifestSignedXml2::.ctor(class [System.Xml]System.Xml.XmlDocument document)
0x9a6b  stloc.1
0x9a6c  ldloc.1
0x9a6d  ldloc.0
0x9a6e  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::set_SigningKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm)
0x9a73  ldloc.1
0x9a74  callvirt instance class [System.Security]System.Security.Cryptography.Xml.SignedInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_SignedInfo()
0x9a79  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/10/xml-exc-c14n#"
0x9a7e  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedInfo::set_CanonicalizationMethod(string)
0x9a83  ldarg.1
0x9a84  callvirt instance bool System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_UseSha256()
0x9a89  brfalse.s loc_9A9B
0x9a8b  ldloc.1
0x9a8c  callvirt instance class [System.Security]System.Security.Cryptography.Xml.SignedInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_SignedInfo()
0x9a91  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x9a96  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedInfo::set_SignatureMethod(string)
0x9a9b  ldloc.1
0x9a9c  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x9aa1  ldloc.0
0x9aa2  newobj   instance void [System.Security]System.Security.Cryptography.Xml.RSAKeyValue::.ctor(class [mscorlib]System.Security.Cryptography.RSA)
0x9aa7  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::AddClause(class [System.Security]System.Security.Cryptography.Xml.KeyInfoClause)
0x9aac  ldloc.1
0x9aad  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x9ab2  ldarg.1
0x9ab3  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_Certificate()
0x9ab8  ldarg.1
0x9ab9  callvirt instance valuetype [System]System.Security.Cryptography.X509Certificates.X509IncludeOption System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_IncludeOption()
0x9abe  newobj   instance void [System.Security]System.Security.Cryptography.Xml.KeyInfoX509Data::.ctor(class [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate, valuetype [System]System.Security.Cryptography.X509Certificates.X509IncludeOption)
0x9ac3  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::AddClause(class [System.Security]System.Security.Cryptography.Xml.KeyInfoClause)
0x9ac8  newobj   instance void [System.Security]System.Security.Cryptography.Xml.Reference::.ctor()
0x9acd  stloc.2
0x9ace  ldloc.2
0x9acf  ldstr    asc_2F208// ""
0x9ad4  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::set_Uri(string)
0x9ad9  ldarg.1
0x9ada  callvirt instance bool System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_UseSha256()
0x9adf  brfalse.s loc_9AEC
0x9ae1  ldloc.2
0x9ae2  ldstr    aHttpWwwW3Org20_7// "http://www.w3.org/2000/09/xmldsig#sha25"...
0x9ae7  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::set_DigestMethod(string)
0x9aec  ldloc.2
0x9aed  newobj   instance void [System.Security]System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform::.ctor()
0x9af2  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::AddTransform(class [System.Security]System.Security.Cryptography.Xml.Transform)
0x9af7  ldloc.2
0x9af8  newobj   instance void [System.Security]System.Security.Cryptography.Xml.XmlDsigExcC14NTransform::.ctor()
0x9afd  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::AddTransform(class [System.Security]System.Security.Cryptography.Xml.Transform)
0x9b02  ldloc.1
0x9b03  ldloc.2
0x9b04  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::AddReference(class [System.Security]System.Security.Cryptography.Xml.Reference)
0x9b09  ldloc.1
0x9b0a  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::ComputeSignature()
0x9b0f  ldloc.1
0x9b10  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Security]System.Security.Cryptography.Xml.SignedXml::GetXml()
0x9b15  stloc.3
0x9b16  ldloc.3
0x9b17  ldstr    aId_2// "Id"
0x9b1c  ldstr    aAuthenticodesi// "AuthenticodeSignature"
0x9b21  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x9b26  ldarg.0
0x9b27  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x9b2c  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x9b31  stloc.s  4
0x9b33  ldloc.s  4
0x9b35  ldstr    aR// "r"
0x9b3a  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x9b3f  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9b44  ldarg.0
0x9b45  ldstr    aRLicenseRIssue// "r:license/r:issuer"
0x9b4a  ldloc.s  4
0x9b4c  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9b51  isinst   [System.Xml]System.Xml.XmlElement
0x9b56  stloc.s  5
0x9b58  ldloc.s  5
0x9b5a  ldarg.0
0x9b5b  ldloc.3
0x9b5c  ldc.i4.1
0x9b5d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x9b62  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x9b67  pop
0x9b68  ldarg.2
0x9b69  brfalse.s loc_9B7B
0x9b6b  ldarg.2
0x9b6c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9b71  brfalse.s loc_9B7B
0x9b73  ldarg.0
0x9b74  ldarg.2
0x9b75  ldarg.3
0x9b76  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::TimestampSignedLicenseDom(class [System.Xml]System.Xml.XmlDocument licenseDom, string timeStampUrl, bool useSha256)
0x9b7b  ldarg.0
0x9b7c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x9b81  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x9b86  ldstr    aMsrelReldataXm// "<msrel:RelData xmlns:msrel=\"http://sch"...
0x9b8b  ldarg.0
0x9b8c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x9b91  ldstr    aMsrelReldata// "</msrel:RelData>"
0x9b96  call     string [mscorlib]System.String::Concat(string, string, string)
0x9b9b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x9ba0  leave.s  loc_9BAC
0x9ba2  ldloc.0
0x9ba3  brfalse.s loc_9BAB
0x9ba5  ldloc.0
0x9ba6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9bab  endfinally
0x9bac  ret
```
