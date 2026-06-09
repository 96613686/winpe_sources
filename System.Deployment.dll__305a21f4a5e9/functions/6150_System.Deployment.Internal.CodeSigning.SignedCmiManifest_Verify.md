# System.Deployment.Internal.CodeSigning.SignedCmiManifest::Verify

- ea: `0x6150`
- end: `0x63d7`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::Verify`
- size: `647`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x25a00`

## callees

- `0x5fb0`
- `0x6150`
- `0x6400`
- `0x68d0`
- `0x75a0`
- `0x75d0`
- `0x7610`

## string_xrefs

- `0x6175`: `http://www.w3.org/2000/09/xmldsig#`
- `0x62e0`: `http://www.w3.org/2001/10/xml-exc-c14n#`
- `0x62fb`: `http://www.w3.org/2000/09/xmldsig#enveloped-signature`

## pseudocode

```c

```

## disassembly

```asm
0x6150  ldarg.0
0x6151  ldnull
0x6152  stfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_strongNameSignerInfo
0x6157  ldarg.0
0x6158  ldnull
0x6159  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_authenticodeSignerInfo
0x615e  ldarg.0
0x615f  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6164  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x6169  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x616e  stloc.0
0x616f  ldloc.0
0x6170  ldstr    aDs// "ds"
0x6175  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x617a  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x617f  ldarg.0
0x6180  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6185  ldstr    aDsSignature// "//ds:Signature"
0x618a  ldloc.0
0x618b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6190  isinst   [System.Xml]System.Xml.XmlElement
0x6195  stloc.1
0x6196  ldloc.1
0x6197  brtrue.s loc_61A4
0x6199  ldc.i4   0x800B0100
0x619e  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x61a3  throw
0x61a4  ldstr    aId_2// "Id"
0x61a9  stloc.2
0x61aa  ldloc.1
0x61ab  ldloc.2
0x61ac  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x61b1  brtrue.s loc_61DC
0x61b3  ldstr    aId_3// "id"
0x61b8  stloc.2
0x61b9  ldloc.1
0x61ba  ldloc.2
0x61bb  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x61c0  brtrue.s loc_61DC
0x61c2  ldstr    aId_4// "ID"
0x61c7  stloc.2
0x61c8  ldloc.1
0x61c9  ldloc.2
0x61ca  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x61cf  brtrue.s loc_61DC
0x61d1  ldc.i4   0x800B0003
0x61d6  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x61db  throw
0x61dc  ldloc.1
0x61dd  ldloc.2
0x61de  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x61e3  stloc.3
0x61e4  ldloc.3
0x61e5  brfalse.s loc_61F5
0x61e7  ldloc.3
0x61e8  ldstr    aStrongnamesign// "StrongNameSignature"
0x61ed  ldc.i4.4
0x61ee  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x61f3  brfalse.s loc_6200
0x61f5  ldc.i4   0x800B0003
0x61fa  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x61ff  throw
0x6200  ldc.i4.0
0x6201  stloc.s  4
0x6203  ldloc.1
0x6204  ldstr    aDsSignedinfoDs// "ds:SignedInfo/ds:Reference"
0x6209  ldloc.0
0x620a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x620f  stloc.s  5
0x6211  ldloc.s  5
0x6213  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6218  stloc.s  0xA
0x621a  br       loc_6325
0x621f  ldloc.s  0xA
0x6221  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6226  castclass [System.Xml]System.Xml.XmlNode
0x622b  stloc.s  0xB
0x622d  ldloc.s  0xB
0x622f  isinst   [System.Xml]System.Xml.XmlElement
0x6234  stloc.s  0xC
0x6236  ldloc.s  0xC
0x6238  brfalse  loc_6325
0x623d  ldloc.s  0xC
0x623f  ldstr    aUri// "URI"
0x6244  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x6249  brfalse  loc_6325
0x624e  ldloc.s  0xC
0x6250  ldstr    aUri// "URI"
0x6255  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x625a  stloc.s  0xD
0x625c  ldloc.s  0xD
0x625e  brfalse  loc_6325
0x6263  ldloc.s  0xD
0x6265  callvirt instance int32 [mscorlib]System.String::get_Length()
0x626a  brtrue   loc_6325
0x626f  ldloc.s  0xC
0x6271  ldstr    aDsTransforms// "ds:Transforms"
0x6276  ldloc.0
0x6277  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x627c  stloc.s  0xE
0x627e  ldloc.s  0xE
0x6280  brtrue.s loc_628D
0x6282  ldc.i4   0x800B0003
0x6287  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x628c  throw
0x628d  ldloc.s  0xE
0x628f  ldstr    aDsTransform// "ds:Transform"
0x6294  ldloc.0
0x6295  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x629a  stloc.s  0xF
0x629c  ldloc.s  0xF
0x629e  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x62a3  ldc.i4.2
0x62a4  bge.s    loc_62B1
0x62a6  ldc.i4   0x800B0003
0x62ab  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x62b0  throw
0x62b1  ldc.i4.0
0x62b2  stloc.s  0x10
0x62b4  ldc.i4.0
0x62b5  stloc.s  0x11
0x62b7  ldc.i4.0
0x62b8  stloc.s  0x12
0x62ba  br.s     loc_631A
0x62bc  ldloc.s  0xF
0x62be  ldloc.s  0x12
0x62c0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x62c5  isinst   [System.Xml]System.Xml.XmlElement
0x62ca  stloc.s  0x13
0x62cc  ldloc.s  0x13
0x62ce  ldstr    aAlgorithm// "Algorithm"
0x62d3  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x62d8  stloc.s  0x14
0x62da  ldloc.s  0x14
0x62dc  brfalse.s loc_6325
0x62de  ldloc.s  0x14
0x62e0  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/10/xml-exc-c14n#"
0x62e5  ldc.i4.4
0x62e6  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x62eb  brfalse.s loc_62F9
0x62ed  ldc.i4.1
0x62ee  stloc.s  0x10
0x62f0  ldloc.s  0x11
0x62f2  brfalse.s loc_6314
0x62f4  ldc.i4.1
0x62f5  stloc.s  4
0x62f7  br.s     loc_6325
0x62f9  ldloc.s  0x14
0x62fb  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/09/xmldsig#envel"...
0x6300  ldc.i4.4
0x6301  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6306  brfalse.s loc_6314
0x6308  ldc.i4.1
0x6309  stloc.s  0x11
0x630b  ldloc.s  0x10
0x630d  brfalse.s loc_6314
0x630f  ldc.i4.1
0x6310  stloc.s  4
0x6312  br.s     loc_6325
0x6314  ldloc.s  0x12
0x6316  ldc.i4.1
0x6317  add
0x6318  stloc.s  0x12
0x631a  ldloc.s  0x12
0x631c  ldloc.s  0xF
0x631e  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x6323  blt.s    loc_62BC
0x6325  ldloc.s  0xA
0x6327  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x632c  brtrue   loc_621F
0x6331  leave.s  loc_6348
0x6333  ldloc.s  0xA
0x6335  isinst   [mscorlib]System.IDisposable
0x633a  stloc.s  0x15
0x633c  ldloc.s  0x15
0x633e  brfalse.s loc_6347
0x6340  ldloc.s  0x15
0x6342  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6347  endfinally
0x6348  ldloc.s  4
0x634a  brtrue.s loc_6357
0x634c  ldc.i4   0x800B0003
0x6351  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6356  throw
0x6357  ldarg.0
0x6358  call     instance string System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyPublicKeyToken()
0x635d  stloc.s  6
0x635f  ldarg.0
0x6360  ldc.i4   0x800B010B
0x6365  ldloc.s  6
0x6367  newobj   instance void System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo::.ctor(int32 errorCode, string publicKeyToken)
0x636c  stfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_strongNameSignerInfo
0x6371  ldarg.0
0x6372  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6377  ldc.i4.1
0x6378  newobj   instance void System.Deployment.Internal.CodeSigning.ManifestSignedXml::.ctor(class [System.Xml]System.Xml.XmlDocument document, bool verify)
0x637d  stloc.s  7
0x637f  ldloc.s  7
0x6381  ldloc.1
0x6382  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::LoadXml(class [System.Xml]System.Xml.XmlElement)
0x6387  ldnull
0x6388  stloc.s  8
0x638a  ldloc.s  7
0x638c  ldloca.s 8
0x638e  callvirt instance bool [System.Security]System.Security.Cryptography.Xml.SignedXml::CheckSignatureReturningKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm&)
0x6393  stloc.s  9
0x6395  ldarg.0
0x6396  ldfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_strongNameSignerInfo
0x639b  ldloc.s  8
0x639d  callvirt instance void System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo::set_PublicKey(class [mscorlib]System.Security.Cryptography.AsymmetricAlgorithm value)
0x63a2  ldloc.s  9
0x63a4  brtrue.s loc_63C1
0x63a6  ldarg.0
0x63a7  ldfld    class System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_strongNameSignerInfo
0x63ac  ldc.i4   0x80096010
0x63b1  callvirt instance void System.Deployment.Internal.CodeSigning.CmiStrongNameSignerInfo::set_ErrorCode(int32 value)
0x63b6  ldc.i4   0x80096010
0x63bb  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x63c0  throw
0x63c1  ldarg.1
0x63c2  ldc.i4   0x10000
0x63c7  and
0x63c8  ldc.i4   0x10000
0x63cd  beq.s    loc_63D6
0x63cf  ldarg.0
0x63d0  ldarg.1
0x63d1  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyLicense(valuetype System.Deployment.Internal.CodeSigning.CmiManifestVerifyFlags verifyFlags)
0x63d6  ret
```
