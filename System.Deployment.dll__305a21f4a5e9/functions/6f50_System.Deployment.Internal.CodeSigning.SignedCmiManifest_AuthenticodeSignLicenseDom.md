# System.Deployment.Internal.CodeSigning.SignedCmiManifest::AuthenticodeSignLicenseDom

- ea: `0x6f50`
- end: `0x707f`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::AuthenticodeSignLicenseDom`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60b0`

## callees

- `0x5fa0`
- `0x6f50`
- `0x7080`
- `0x74b0`
- `0x7510`
- `0x27400`
- `0x27460`

## string_xrefs

- `0x6f83`: `http://www.w3.org/2001/10/xml-exc-c14n#`
- `0x7064`: `<msrel:RelData xmlns:msrel="http://schemas.microsoft.com/windows/rel/2005/reldata">`

## pseudocode

```c

```

## disassembly

```asm
0x6f50  ldarg.1
0x6f51  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Certificate()
0x6f56  call     class [mscorlib]System.Security.Cryptography.RSA System.Security.Cryptography.CngLightup::GetRSAPublicKey(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 cert)
0x6f5b  stloc.0
0x6f5c  ldloc.0
0x6f5d  brtrue.s loc_6F65
0x6f5f  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x6f64  throw
0x6f65  ldarg.0
0x6f66  newobj   instance void System.Deployment.Internal.CodeSigning.ManifestSignedXml::.ctor(class [System.Xml]System.Xml.XmlDocument document)
0x6f6b  stloc.1
0x6f6c  ldloc.1
0x6f6d  ldarg.1
0x6f6e  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Certificate()
0x6f73  call     class [mscorlib]System.Security.Cryptography.RSA System.Security.Cryptography.CngLightup::GetRSAPrivateKey(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 cert)
0x6f78  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::set_SigningKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm)
0x6f7d  ldloc.1
0x6f7e  callvirt instance class [System.Security]System.Security.Cryptography.Xml.SignedInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_SignedInfo()
0x6f83  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/10/xml-exc-c14n#"
0x6f88  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedInfo::set_CanonicalizationMethod(string)
0x6f8d  ldloc.1
0x6f8e  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x6f93  ldloc.0
0x6f94  newobj   instance void [System.Security]System.Security.Cryptography.Xml.RSAKeyValue::.ctor(class [mscorlib]System.Security.Cryptography.RSA)
0x6f99  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::AddClause(class [System.Security]System.Security.Cryptography.Xml.KeyInfoClause)
0x6f9e  ldloc.1
0x6f9f  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x6fa4  ldarg.1
0x6fa5  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Certificate()
0x6faa  ldarg.1
0x6fab  callvirt instance valuetype [System]System.Security.Cryptography.X509Certificates.X509IncludeOption System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_IncludeOption()
0x6fb0  newobj   instance void [System.Security]System.Security.Cryptography.Xml.KeyInfoX509Data::.ctor(class [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate, valuetype [System]System.Security.Cryptography.X509Certificates.X509IncludeOption)
0x6fb5  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::AddClause(class [System.Security]System.Security.Cryptography.Xml.KeyInfoClause)
0x6fba  newobj   instance void [System.Security]System.Security.Cryptography.Xml.Reference::.ctor()
0x6fbf  stloc.2
0x6fc0  ldloc.2
0x6fc1  ldstr    asc_2F208// ""
0x6fc6  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::set_Uri(string)
0x6fcb  ldloc.2
0x6fcc  newobj   instance void [System.Security]System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform::.ctor()
0x6fd1  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::AddTransform(class [System.Security]System.Security.Cryptography.Xml.Transform)
0x6fd6  ldloc.2
0x6fd7  newobj   instance void [System.Security]System.Security.Cryptography.Xml.XmlDsigExcC14NTransform::.ctor()
0x6fdc  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::AddTransform(class [System.Security]System.Security.Cryptography.Xml.Transform)
0x6fe1  ldloc.1
0x6fe2  ldloc.2
0x6fe3  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::AddReference(class [System.Security]System.Security.Cryptography.Xml.Reference)
0x6fe8  ldloc.1
0x6fe9  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::ComputeSignature()
0x6fee  ldloc.1
0x6fef  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Security]System.Security.Cryptography.Xml.SignedXml::GetXml()
0x6ff4  stloc.3
0x6ff5  ldloc.3
0x6ff6  ldstr    aId_2// "Id"
0x6ffb  ldstr    aAuthenticodesi// "AuthenticodeSignature"
0x7000  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x7005  ldarg.0
0x7006  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x700b  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x7010  stloc.s  4
0x7012  ldloc.s  4
0x7014  ldstr    aR// "r"
0x7019  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x701e  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7023  ldarg.0
0x7024  ldstr    aRLicenseRIssue// "r:license/r:issuer"
0x7029  ldloc.s  4
0x702b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x7030  isinst   [System.Xml]System.Xml.XmlElement
0x7035  stloc.s  5
0x7037  ldloc.s  5
0x7039  ldarg.0
0x703a  ldloc.3
0x703b  ldc.i4.1
0x703c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x7041  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x7046  pop
0x7047  ldarg.2
0x7048  brfalse.s loc_7059
0x704a  ldarg.2
0x704b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x7050  brfalse.s loc_7059
0x7052  ldarg.0
0x7053  ldarg.2
0x7054  call     void System.Deployment.Internal.CodeSigning.SignedCmiManifest::TimestampSignedLicenseDom(class [System.Xml]System.Xml.XmlDocument licenseDom, string timeStampUrl)
0x7059  ldarg.0
0x705a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x705f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x7064  ldstr    aMsrelReldataXm// "<msrel:RelData xmlns:msrel=\"http://sch"...
0x7069  ldarg.0
0x706a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x706f  ldstr    aMsrelReldata// "</msrel:RelData>"
0x7074  call     string [mscorlib]System.String::Concat(string, string, string)
0x7079  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x707e  ret
```
