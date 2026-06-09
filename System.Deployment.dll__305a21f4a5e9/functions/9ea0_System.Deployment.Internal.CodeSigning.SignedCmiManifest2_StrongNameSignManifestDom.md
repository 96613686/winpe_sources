# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::StrongNameSignManifestDom

- ea: `0x9ea0`
- end: `0xa00f`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::StrongNameSignManifestDom`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7a80`

## callees

- `0x78f0`
- `0x9600`
- `0x9ea0`
- `0xa100`
- `0xa220`
- `0xa230`

## string_xrefs

- `0x9f43`: `http://www.w3.org/2001/10/xml-exc-c14n#`
- `0x9ec7`: `urn:schemas-microsoft-com:asm.v1`
- `0x9f5b`: `http://www.w3.org/2000/09/xmldsig#rsa-sha256`
- `0x9fbc`: `http://www.w3.org/2000/09/xmldsig#sha256`

## pseudocode

```c

```

## disassembly

```asm
0x9ea0  ldarg.2
0x9ea1  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_StrongNameKey()
0x9ea6  isinst   [mscorlib]System.Security.Cryptography.RSA
0x9eab  stloc.0
0x9eac  ldloc.0
0x9ead  brtrue.s loc_9EB5
0x9eaf  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x9eb4  throw
0x9eb5  ldarg.0
0x9eb6  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x9ebb  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x9ec0  stloc.1
0x9ec1  ldloc.1
0x9ec2  ldstr    aAsm// "asm"
0x9ec7  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x9ecc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9ed1  ldarg.0
0x9ed2  ldstr    aAsmAssembly// "asm:assembly"
0x9ed7  ldloc.1
0x9ed8  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9edd  isinst   [System.Xml]System.Xml.XmlElement
0x9ee2  stloc.2
0x9ee3  ldloc.2
0x9ee4  brtrue.s loc_9EF1
0x9ee6  ldc.i4   0x800B0003
0x9eeb  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9ef0  throw
0x9ef1  ldarg.2
0x9ef2  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_StrongNameKey()
0x9ef7  isinst   [mscorlib]System.Security.Cryptography.RSA
0x9efc  brtrue.s loc_9F04
0x9efe  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x9f03  throw
0x9f04  ldloc.2
0x9f05  newobj   instance void System.Deployment.Internal.CodeSigning.ManifestSignedXml2::.ctor(class [System.Xml]System.Xml.XmlElement elem)
0x9f0a  stloc.3
0x9f0b  ldarg.2
0x9f0c  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_StrongNameKey()
0x9f11  isinst   [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider
0x9f16  brfalse.s loc_9F31
0x9f18  ldloc.3
0x9f19  ldarg.2
0x9f1a  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_StrongNameKey()
0x9f1f  isinst   [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider
0x9f24  ldarg.3
0x9f25  call     class [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetFixedRSACryptoServiceProvider(class [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider oldCsp, bool useSha256)
0x9f2a  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::set_SigningKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm)
0x9f2f  br.s     loc_9F3D
0x9f31  ldloc.3
0x9f32  ldarg.2
0x9f33  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_StrongNameKey()
0x9f38  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::set_SigningKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm)
0x9f3d  ldloc.3
0x9f3e  callvirt instance class [System.Security]System.Security.Cryptography.Xml.SignedInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_SignedInfo()
0x9f43  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/10/xml-exc-c14n#"
0x9f48  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedInfo::set_CanonicalizationMethod(string)
0x9f4d  ldarg.2
0x9f4e  callvirt instance bool System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_UseSha256()
0x9f53  brfalse.s loc_9F65
0x9f55  ldloc.3
0x9f56  callvirt instance class [System.Security]System.Security.Cryptography.Xml.SignedInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_SignedInfo()
0x9f5b  ldstr    aHttpWwwW3Org20_6// "http://www.w3.org/2000/09/xmldsig#rsa-s"...
0x9f60  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedInfo::set_SignatureMethod(string)
0x9f65  ldloc.3
0x9f66  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x9f6b  ldloc.0
0x9f6c  newobj   instance void [System.Security]System.Security.Cryptography.Xml.RSAKeyValue::.ctor(class [mscorlib]System.Security.Cryptography.RSA)
0x9f71  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::AddClause(class [System.Security]System.Security.Cryptography.Xml.KeyInfoClause)
0x9f76  ldarg.1
0x9f77  brfalse.s loc_9F8F
0x9f79  ldloc.3
0x9f7a  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x9f7f  ldarg.1
0x9f80  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x9f85  newobj   instance void [System.Security]System.Security.Cryptography.Xml.KeyInfoNode::.ctor(class [System.Xml]System.Xml.XmlElement)
0x9f8a  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::AddClause(class [System.Security]System.Security.Cryptography.Xml.KeyInfoClause)
0x9f8f  ldloc.3
0x9f90  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x9f95  ldstr    aStrongnamekeyi// "StrongNameKeyInfo"
0x9f9a  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::set_Id(string)
0x9f9f  newobj   instance void [System.Security]System.Security.Cryptography.Xml.Reference::.ctor()
0x9fa4  stloc.s  4
0x9fa6  ldloc.s  4
0x9fa8  ldstr    asc_2F208// ""
0x9fad  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::set_Uri(string)
0x9fb2  ldarg.2
0x9fb3  callvirt instance bool System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_UseSha256()
0x9fb8  brfalse.s loc_9FC6
0x9fba  ldloc.s  4
0x9fbc  ldstr    aHttpWwwW3Org20_7// "http://www.w3.org/2000/09/xmldsig#sha25"...
0x9fc1  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::set_DigestMethod(string)
0x9fc6  ldloc.s  4
0x9fc8  newobj   instance void [System.Security]System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform::.ctor()
0x9fcd  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::AddTransform(class [System.Security]System.Security.Cryptography.Xml.Transform)
0x9fd2  ldloc.s  4
0x9fd4  newobj   instance void [System.Security]System.Security.Cryptography.Xml.XmlDsigExcC14NTransform::.ctor()
0x9fd9  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::AddTransform(class [System.Security]System.Security.Cryptography.Xml.Transform)
0x9fde  ldloc.3
0x9fdf  ldloc.s  4
0x9fe1  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::AddReference(class [System.Security]System.Security.Cryptography.Xml.Reference)
0x9fe6  ldloc.3
0x9fe7  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::ComputeSignature()
0x9fec  ldloc.3
0x9fed  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Security]System.Security.Cryptography.Xml.SignedXml::GetXml()
0x9ff2  stloc.s  5
0x9ff4  ldloc.s  5
0x9ff6  ldstr    aId_2// "Id"
0x9ffb  ldstr    aStrongnamesign// "StrongNameSignature"
0xa000  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa005  ldloc.2
0xa006  ldloc.s  5
0xa008  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xa00d  pop
0xa00e  ret
```
