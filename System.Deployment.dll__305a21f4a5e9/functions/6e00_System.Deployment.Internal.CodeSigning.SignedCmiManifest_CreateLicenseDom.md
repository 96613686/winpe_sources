# System.Deployment.Internal.CodeSigning.SignedCmiManifest::CreateLicenseDom

- ea: `0x6e00`
- end: `0x6f4b`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::CreateLicenseDom`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60b0`

## callees

- `0x6e00`
- `0x72e0`
- `0x74b0`
- `0x74c0`
- `0x74e0`

## string_xrefs

- `0x6e3a`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`
- `0x6e0e`: `<r:license xmlns:r="urn:mpeg:mpeg21:2003:01-REL-R-NS" xmlns:as="http://schemas.microsoft.com/windows/pki/2005/Authenticode"><r:grant><as:ManifestInformation><as:assemblyIdentity /></as:ManifestInformation><as:SignedBy/><as:AuthenticodePublisher><as:X509SubjectName>CN=dummy</as:X509SubjectName></as:AuthenticodePublisher></r:grant><r:issuer></r:issuer></r:license>`
- `0x6e45`: `r:license/r:grant/as:ManifestInformation/as:assemblyIdentity`
- `0x6eae`: `r:license/r:grant/as:ManifestInformation`

## pseudocode

```c

```

## disassembly

```asm
0x6e00  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x6e05  stloc.0
0x6e06  ldloc.0
0x6e07  ldc.i4.1
0x6e08  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_PreserveWhitespace(bool)
0x6e0d  ldloc.0
0x6e0e  ldstr    aRLicenseXmlnsR// "<r:license xmlns:r=\"urn:mpeg:mpeg21:20"...
0x6e13  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x6e18  ldloc.0
0x6e19  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x6e1e  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x6e23  stloc.1
0x6e24  ldloc.1
0x6e25  ldstr    aR// "r"
0x6e2a  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x6e2f  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6e34  ldloc.1
0x6e35  ldstr    aAs// "as"
0x6e3a  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x6e3f  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6e44  ldloc.0
0x6e45  ldstr    aRLicenseRGrant// "r:license/r:grant/as:ManifestInformatio"...
0x6e4a  ldloc.1
0x6e4b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6e50  isinst   [System.Xml]System.Xml.XmlElement
0x6e55  stloc.2
0x6e56  ldloc.2
0x6e57  callvirt instance void [System.Xml]System.Xml.XmlElement::RemoveAllAttributes()
0x6e5c  ldarg.1
0x6e5d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6e62  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNamedNodeMap::GetEnumerator()
0x6e67  stloc.s  5
0x6e69  br.s     loc_6E8D
0x6e6b  ldloc.s  5
0x6e6d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6e72  castclass [System.Xml]System.Xml.XmlAttribute
0x6e77  stloc.s  6
0x6e79  ldloc.2
0x6e7a  ldloc.s  6
0x6e7c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x6e81  ldloc.s  6
0x6e83  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6e88  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6e8d  ldloc.s  5
0x6e8f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e94  brtrue.s loc_6E6B
0x6e96  leave.s  loc_6EAD
0x6e98  ldloc.s  5
0x6e9a  isinst   [mscorlib]System.IDisposable
0x6e9f  stloc.s  7
0x6ea1  ldloc.s  7
0x6ea3  brfalse.s loc_6EAC
0x6ea5  ldloc.s  7
0x6ea7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6eac  endfinally
0x6ead  ldloc.0
0x6eae  ldstr    aRLicenseRGrant_0// "r:license/r:grant/as:ManifestInformatio"...
0x6eb3  ldloc.1
0x6eb4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6eb9  isinst   [System.Xml]System.Xml.XmlElement
0x6ebe  stloc.3
0x6ebf  ldloc.3
0x6ec0  ldstr    aHash// "Hash"
0x6ec5  ldarg.2
0x6ec6  ldlen
0x6ec7  brfalse.s loc_6ED5
0x6ec9  ldarg.2
0x6eca  ldc.i4.0
0x6ecb  ldarg.2
0x6ecc  ldlen
0x6ecd  conv.i4
0x6ece  call     string System.Deployment.Internal.CodeSigning.SignedCmiManifest::BytesToHexString(unsigned int8[] array, int32 start, int32 end)
0x6ed3  br.s     loc_6EDA
0x6ed5  ldstr    asc_2F208// ""
0x6eda  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6edf  ldloc.3
0x6ee0  ldstr    aDescription// "Description"
0x6ee5  ldarg.0
0x6ee6  callvirt instance string System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Description()
0x6eeb  brfalse.s loc_6EF5
0x6eed  ldarg.0
0x6eee  callvirt instance string System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Description()
0x6ef3  br.s     loc_6EFA
0x6ef5  ldstr    asc_2F208// ""
0x6efa  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6eff  ldloc.3
0x6f00  ldstr    aUrl// "Url"
0x6f05  ldarg.0
0x6f06  callvirt instance string System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_DescriptionUrl()
0x6f0b  brfalse.s loc_6F15
0x6f0d  ldarg.0
0x6f0e  callvirt instance string System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_DescriptionUrl()
0x6f13  br.s     loc_6F1A
0x6f15  ldstr    asc_2F208// ""
0x6f1a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6f1f  ldloc.0
0x6f20  ldstr    aRLicenseRGrant_1// "r:license/r:grant/as:AuthenticodePublis"...
0x6f25  ldloc.1
0x6f26  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6f2b  isinst   [System.Xml]System.Xml.XmlElement
0x6f30  stloc.s  4
0x6f32  ldloc.s  4
0x6f34  ldarg.0
0x6f35  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner::get_Certificate()
0x6f3a  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x6f3f  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x6f44  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6f49  ldloc.0
0x6f4a  ret
```
