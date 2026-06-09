# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyLicenseNew

- ea: `0x7e60`
- end: `0x829c`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyLicenseNew`
- size: `1084`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7b40`

## callees

- `0x7640`
- `0x7730`
- `0x7770`
- `0x7790`
- `0x77b0`
- `0x77e0`
- `0x7900`
- `0x7c70`
- `0x7e60`
- `0x82a0`
- `0x8470`
- `0x8620`
- `0x86e0`
- `0x8810`
- `0x8e10`
- `0x8ec0`
- `0x8f30`
- `0x8fe0`
- `0x90d0`
- `0xa100`
- `0xa3b0`

## string_xrefs

- `0x7e97`: `http://www.w3.org/2000/09/xmldsig#`
- `0x7e77`: `urn:schemas-microsoft-com:asm.v1`
- `0x7e87`: `urn:schemas-microsoft-com:asm.v2`
- `0x7ea7`: `http://schemas.microsoft.com/windows/rel/2005/reldata`
- `0x7ec7`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`

## pseudocode

```c

```

## disassembly

```asm
0x7e60  ldarg.0
0x7e61  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7e66  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x7e6b  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x7e70  stloc.0
0x7e71  ldloc.0
0x7e72  ldstr    aAsm// "asm"
0x7e77  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x7e7c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7e81  ldloc.0
0x7e82  ldstr    aAsm2// "asm2"
0x7e87  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x7e8c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7e91  ldloc.0
0x7e92  ldstr    aDs// "ds"
0x7e97  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x7e9c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7ea1  ldloc.0
0x7ea2  ldstr    aMsrel// "msrel"
0x7ea7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/windows/re"...
0x7eac  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7eb1  ldloc.0
0x7eb2  ldstr    aR// "r"
0x7eb7  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x7ebc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7ec1  ldloc.0
0x7ec2  ldstr    aAs// "as"
0x7ec7  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x7ecc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7ed1  ldarg.0
0x7ed2  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7ed7  ldstr    aAsmAssemblyDsS// "asm:assembly/ds:Signature/ds:KeyInfo/ms"...
0x7edc  ldloc.0
0x7edd  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x7ee2  isinst   [System.Xml]System.Xml.XmlElement
0x7ee7  stloc.1
0x7ee8  ldloc.1
0x7ee9  brtrue.s loc_7EEC
0x7eeb  ret
0x7eec  ldarg.0
0x7eed  ldloc.0
0x7eee  ldarg.2
0x7eef  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyAssemblyIdentity(class [System.Xml]System.Xml.XmlNamespaceManager nsm, valuetype System.Deployment.Internal.CodeSigning.SupportedHashAlgorithm hashAlgorithm)
0x7ef4  ldarg.0
0x7ef5  ldc.i4   0x800B010B
0x7efa  newobj   instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::.ctor(int32 errorCode)
0x7eff  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7f04  ldloc.1
0x7f05  ldstr    aRIssuerDsSigna_0// "//r:issuer/ds:Signature"
0x7f0a  ldloc.0
0x7f0b  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x7f10  isinst   [System.Xml]System.Xml.XmlElement
0x7f15  stloc.2
0x7f16  ldloc.2
0x7f17  brtrue.s loc_7F24
0x7f19  ldc.i4   0x800B0100
0x7f1e  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x7f23  throw
0x7f24  ldarg.0
0x7f25  ldloc.2
0x7f26  ldstr    aAuthenticodesi// "AuthenticodeSignature"
0x7f2b  ldloc.0
0x7f2c  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureForm(class [System.Xml]System.Xml.XmlElement signatureNode, string signatureKind, class [System.Xml]System.Xml.XmlNamespaceManager nsm)
0x7f31  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x7f36  stloc.3
0x7f37  ldloc.3
0x7f38  ldloc.1
0x7f39  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x7f3e  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x7f43  ldloc.3
0x7f44  ldstr    aRIssuerDsSigna_0// "//r:issuer/ds:Signature"
0x7f49  ldloc.0
0x7f4a  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x7f4f  isinst   [System.Xml]System.Xml.XmlElement
0x7f54  stloc.2
0x7f55  ldloc.3
0x7f56  newobj   instance void System.Deployment.Internal.CodeSigning.ManifestSignedXml2::.ctor(class [System.Xml]System.Xml.XmlDocument document)
0x7f5b  stloc.s  4
0x7f5d  ldloc.s  4
0x7f5f  ldloc.2
0x7f60  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedXml::LoadXml(class [System.Xml]System.Xml.XmlElement)
0x7f65  ldarg.0
0x7f66  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7f6b  brfalse.s loc_7F8A
0x7f6d  ldloc.s  4
0x7f6f  callvirt instance class [System.Security]System.Security.Cryptography.Xml.SignedInfo [System.Security]System.Security.Cryptography.Xml.SignedXml::get_SignedInfo()
0x7f74  ldarg.2
0x7f75  ldarg.0
0x7f76  ldfld    bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_useSha256OrHigher
0x7f7b  ldc.i4   0x80096010
0x7f80  call     string System.Deployment.Internal.CodeSigning.ManifestUtilities::GetSignatureMethodUri(valuetype System.Deployment.Internal.CodeSigning.SupportedHashAlgorithm hashAlgorithm, bool useSha256OrHigher, int32 errorCodeForException)
0x7f85  callvirt instance void [System.Security]System.Security.Cryptography.Xml.SignedInfo::set_SignatureMethod(string)
0x7f8a  ldloc.s  4
0x7f8c  callvirt instance bool [System.Security]System.Security.Cryptography.Xml.SignedXml::CheckSignature()
0x7f91  brtrue.s loc_7FA5
0x7f93  ldarg.0
0x7f94  ldnull
0x7f95  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7f9a  ldc.i4   0x80096004
0x7f9f  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x7fa4  throw
0x7fa5  ldarg.0
0x7fa6  ldloc.s  4
0x7fa8  ldloc.0
0x7fa9  ldloca.s 5
0x7fab  call     instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSigningCertificate(class System.Deployment.Internal.CodeSigning.ManifestSignedXml2 signedXml, class [System.Xml]System.Xml.XmlNamespaceManager nsm, [out] class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection& intermediateCertificates)
0x7fb0  stloc.s  6
0x7fb2  ldc.i4.4
0x7fb3  ldc.i4.1
0x7fb4  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Store::.ctor(valuetype [System]System.Security.Cryptography.X509Certificates.StoreName, valuetype [System]System.Security.Cryptography.X509Certificates.StoreLocation)
0x7fb9  stloc.s  7
0x7fbb  ldloc.s  7
0x7fbd  ldc.i4.4
0x7fbe  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509Store::Open(valuetype [System]System.Security.Cryptography.X509Certificates.OpenFlags)
0x7fc3  ldnull
0x7fc4  stloc.s  8
0x7fc6  ldloc.s  7
0x7fc8  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection [System]System.Security.Cryptography.X509Certificates.X509Store::get_Certificates()
0x7fcd  stloc.s  8
0x7fcf  ldloc.s  8
0x7fd1  brtrue.s loc_7FEE
0x7fd3  ldarg.0
0x7fd4  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7fd9  ldc.i4   0x800B010B
0x7fde  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x7fe3  ldc.i4   0x800B010B
0x7fe8  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x7fed  throw
0x7fee  ldloc.s  8
0x7ff0  ldloc.s  6
0x7ff2  callvirt instance bool [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::Contains(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x7ff7  brfalse.s loc_8014
0x7ff9  ldarg.0
0x7ffa  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7fff  ldc.i4   0x800B0111
0x8004  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x8009  ldc.i4   0x800B0111
0x800e  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x8013  throw
0x8014  leave.s  loc_801E
0x8016  ldloc.s  7
0x8018  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509Store::Close()
0x801d  endfinally
0x801e  ldarg.0
0x801f  ldloc.1
0x8020  ldloc.0
0x8021  ldloca.s 9
0x8023  ldloca.s 0xA
0x8025  ldloca.s 0xB
0x8027  call     instance bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetManifestInformation(class [System.Xml]System.Xml.XmlElement licenseNode, class [System.Xml]System.Xml.XmlNamespaceManager nsm, [out] string& hash, [out] string& description, [out] string& url)
0x802c  brtrue.s loc_8049
0x802e  ldarg.0
0x802f  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x8034  ldc.i4   0x800B0003
0x8039  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x803e  ldc.i4   0x800B0003
0x8043  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x8048  throw
0x8049  ldarg.0
0x804a  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x804f  ldloc.s  9
0x8051  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_Hash(string value)
0x8056  ldarg.0
0x8057  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x805c  ldloc.s  0xA
0x805e  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_Description(string value)
0x8063  ldarg.0
0x8064  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x8069  ldloc.s  0xB
0x806b  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_DescriptionUrl(string value)
0x8070  ldarg.0
0x8071  ldloc.0
0x8072  call     instance bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::OverrideTimestampImprovements(class [System.Xml]System.Xml.XmlNamespaceManager nsm)
0x8077  brtrue.s loc_8085
0x8079  ldarg.0
0x807a  ldloc.2
0x807b  ldloc.0
0x807c  ldloca.s 0xC
0x807e  call     instance bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureTimestampNew(class [System.Xml]System.Xml.XmlElement signatureNode, class [System.Xml]System.Xml.XmlNamespaceManager nsm, [out] valuetype [mscorlib]System.DateTime& verificationTime)
0x8083  br.s     loc_808F
0x8085  ldarg.0
0x8086  ldloc.2
0x8087  ldloc.0
0x8088  ldloca.s 0xC
0x808a  call     instance bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureTimestamp(class [System.Xml]System.Xml.XmlElement signatureNode, class [System.Xml]System.Xml.XmlNamespaceManager nsm, [out] valuetype [mscorlib]System.DateTime& verificationTime)
0x808f  stloc.s  0xD
0x8091  ldc.i4.0
0x8092  stloc.s  0xE
0x8094  ldloc.s  0xD
0x8096  brfalse.s loc_80B0
0x8098  ldarg.1
0x8099  ldc.i4.s 0x10
0x809b  and
0x809c  ldc.i4.s 0x10
0x809e  ceq
0x80a0  stloc.s  0xE
0x80a2  ldloc.s  0xE
0x80a4  brtrue.s loc_80B0
0x80a6  ldarg.0
0x80a7  ldloc.s  6
0x80a9  call     instance bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetLifetimeSigning(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 signingCertificate)
0x80ae  stloc.s  0xE
0x80b0  ldarg.0
0x80b1  call     instance unsigned int32 System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetAuthenticodePolicies()
0x80b6  stloc.s  0xF
0x80b8  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Chain::.ctor()
0x80bd  stloc.s  0x10
0x80bf  ldloc.s  0x10
0x80c1  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x80c6  ldc.i4.2
0x80c7  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::set_RevocationFlag(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationFlag)
0x80cc  ldloc.s  0x10
0x80ce  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x80d3  ldc.i4.1
0x80d4  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::set_RevocationMode(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode)
0x80d9  ldc.i4.2
0x80da  ldarg.1
0x80db  and
0x80dc  ldc.i4.2
0x80dd  bne.un.s loc_80EE
0x80df  ldloc.s  0x10
0x80e1  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x80e6  ldc.i4.0
0x80e7  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::set_RevocationFlag(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationFlag)
0x80ec  br.s     loc_8125
0x80ee  ldc.i4.4
0x80ef  ldarg.1
0x80f0  and
0x80f1  ldc.i4.4
0x80f2  bne.un.s loc_8103
0x80f4  ldloc.s  0x10
0x80f6  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x80fb  ldc.i4.1
0x80fc  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::set_RevocationFlag(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationFlag)
0x8101  br.s     loc_8125
0x8103  ldc.i4.1
0x8104  ldarg.1
0x8105  and
0x8106  ldc.i4.1
0x8107  beq.s    loc_8118
0x8109  ldc.i4   0x200
0x810e  ldloc.s  0xF
0x8110  and
0x8111  ldc.i4   0x200
0x8116  bne.un.s loc_8125
0x8118  ldloc.s  0x10
0x811a  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x811f  ldc.i4.0
0x8120  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::set_RevocationMode(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode)
0x8125  ldloc.s  0x10
0x8127  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x812c  ldloc.s  0xC
0x812e  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::set_VerificationTime(valuetype [mscorlib]System.DateTime)
0x8133  ldloc.s  0xD
0x8135  ldloc.s  0xE
0x8137  and
0x8138  brfalse.s loc_8156
0x813a  ldloc.s  0x10
0x813c  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x8141  callvirt instance class [System]System.Security.Cryptography.OidCollection [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::get_ApplicationPolicy()
0x8146  ldstr    a13614131110313// "1.3.6.1.4.1.311.10.3.13"
0x814b  newobj   instance void [System]System.Security.Cryptography.Oid::.ctor(string)
0x8150  callvirt instance int32 [System]System.Security.Cryptography.OidCollection::Add(class [System]System.Security.Cryptography.Oid)
0x8155  pop
0x8156  ldloc.s  0x10
0x8158  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x815d  ldc.i4.0
0x815e  ldc.i4.1
0x815f  ldc.i4.0
0x8160  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x8165  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::set_UrlRetrievalTimeout(valuetype [mscorlib]System.TimeSpan)
0x816a  ldloc.s  0x10
0x816c  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x8171  ldc.i4.0
0x8172  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::set_VerificationFlags(valuetype [System]System.Security.Cryptography.X509Certificates.X509VerificationFlags)
0x8177  ldloc.s  5
0x8179  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x817e  ldc.i4.0
0x817f  ble.s    loc_8194
0x8181  ldloc.s  0x10
0x8183  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x8188  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::get_ExtraStore()
0x818d  ldloc.s  5
0x818f  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::AddRange(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection)
0x8194  ldloc.s  0x10
0x8196  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy [System]System.Security.Cryptography.X509Certificates.X509Chain::get_ChainPolicy()
0x819b  callvirt instance class [System]System.Security.Cryptography.OidCollection [System]System.Security.Cryptography.X509Certificates.X509ChainPolicy::get_ApplicationPolicy()
0x81a0  ldstr    a136155733// "1.3.6.1.5.5.7.3.3"
0x81a5  newobj   instance void [System]System.Security.Cryptography.Oid::.ctor(string)
0x81aa  callvirt instance int32 [System]System.Security.Cryptography.OidCollection::Add(class [System]System.Security.Cryptography.Oid)
0x81af  pop
0x81b0  ldloc.s  0x10
0x81b2  ldloc.s  6
0x81b4  callvirt instance bool [System]System.Security.Cryptography.X509Certificates.X509Chain::Build(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x81b9  brtrue.s loc_81D6
0x81bb  ldarg.0
0x81bc  call     instance class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::get_AuthenticodeSignerInfo()
0x81c1  ldc.i4   0x800B0004
0x81c6  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x81cb  ldc.i4   0x800B0004
  ... truncated ...
```
