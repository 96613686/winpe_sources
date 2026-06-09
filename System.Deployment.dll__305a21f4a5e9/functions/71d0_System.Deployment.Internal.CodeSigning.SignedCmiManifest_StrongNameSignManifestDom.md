# System.Deployment.Internal.CodeSigning.SignedCmiManifest::StrongNameSignManifestDom

- ea: `0x71d0`
- end: `0x72da`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::StrongNameSignManifestDom`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60b0`

## callees

- `0x5f90`
- `0x71d0`
- `0x74a0`

## string_xrefs

- `0x723a`: `http://www.w3.org/2001/10/xml-exc-c14n#`
- `0x71f7`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x71d0  ldarg.2
0x71d1  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_StrongNameKey()
0x71d6  isinst   [mscorlib]System.Security.Cryptography.RSA
0x71db  stloc.0
0x71dc  ldloc.0
0x71dd  brtrue.s loc_71E5
0x71df  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x71e4  throw
0x71e5  ldarg.0
0x71e6  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x71eb  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x71f0  stloc.1
0x71f1  ldloc.1
0x71f2  ldstr    aAsm// "asm"
0x71f7  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x71fc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7201  ldarg.0
0x7202  ldstr    aAsmAssembly// "asm:assembly"
0x7207  ldloc.1
0x7208  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x720d  isinst   [System.Xml]System.Xml.XmlElement
0x7212  stloc.2
0x7213  ldloc.2
0x7214  brtrue.s loc_7221
0x7216  ldc.i4   0x800B0003
0x721b  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x7220  throw
0x7221  ldloc.2
0x7222  newobj   instance void System.Deployment.Internal.CodeSigning.ManifestSignedXml::.ctor(class [System.Xml]System.Xml.XmlElement elem)
0x7227  stloc.3
0x7228  ldloc.3
0x7229  ldarg.2
0x722a  callvirt instance class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_StrongNameKey()
0x722f  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::set_SigningKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm)
0x7234  ldloc.3
0x7235  callvirt instance class [System.Security]System.Security.Cryptography.Xml.SignedInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_SignedInfo()
0x723a  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/10/xml-exc-c14n#"
0x723f  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedInfo::set_CanonicalizationMethod(string)
0x7244  ldloc.3
0x7245  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x724a  ldloc.0
0x724b  newobj   instance void [System.Security]System.Security.Cryptography.Xml.RSAKeyValue::.ctor(class [mscorlib]System.Security.Cryptography.RSA)
0x7250  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::AddClause(class [System.Security]System.Security.Cryptography.Xml.KeyInfoClause)
0x7255  ldarg.1
0x7256  brfalse.s loc_726E
0x7258  ldloc.3
0x7259  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x725e  ldarg.1
0x725f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7264  newobj   instance void [System.Security]System.Security.Cryptography.Xml.KeyInfoNode::.ctor(class [System.Xml]System.Xml.XmlElement)
0x7269  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::AddClause(class [System.Security]System.Security.Cryptography.Xml.KeyInfoClause)
0x726e  ldloc.3
0x726f  callvirt instance class [System.Security]System.Security.Cryptography.Xml.KeyInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_KeyInfo()
0x7274  ldstr    aStrongnamekeyi// "StrongNameKeyInfo"
0x7279  callvirt instance void [System.Security]System.Security.Cryptography.Xml.KeyInfo::set_Id(string)
0x727e  newobj   instance void [System.Security]System.Security.Cryptography.Xml.Reference::.ctor()
0x7283  stloc.s  4
0x7285  ldloc.s  4
0x7287  ldstr    asc_2F208// ""
0x728c  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::set_Uri(string)
0x7291  ldloc.s  4
0x7293  newobj   instance void [System.Security]System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform::.ctor()
0x7298  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::AddTransform(class [System.Security]System.Security.Cryptography.Xml.Transform)
0x729d  ldloc.s  4
0x729f  newobj   instance void [System.Security]System.Security.Cryptography.Xml.XmlDsigExcC14NTransform::.ctor()
0x72a4  callvirt instance void [System.Security]System.Security.Cryptography.Xml.Reference::AddTransform(class [System.Security]System.Security.Cryptography.Xml.Transform)
0x72a9  ldloc.3
0x72aa  ldloc.s  4
0x72ac  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::AddReference(class [System.Security]System.Security.Cryptography.Xml.Reference)
0x72b1  ldloc.3
0x72b2  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::ComputeSignature()
0x72b7  ldloc.3
0x72b8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Security]System.Security.Cryptography.Xml.SignedXml::GetXml()
0x72bd  stloc.s  5
0x72bf  ldloc.s  5
0x72c1  ldstr    aId_2// "Id"
0x72c6  ldstr    aStrongnamesign// "StrongNameSignature"
0x72cb  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x72d0  ldloc.2
0x72d1  ldloc.s  5
0x72d3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x72d8  pop
0x72d9  ret
```
