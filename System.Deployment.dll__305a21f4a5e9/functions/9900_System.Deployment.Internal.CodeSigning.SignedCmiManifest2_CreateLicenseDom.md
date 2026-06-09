# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::CreateLicenseDom

- ea: `0x9900`
- end: `0x9a4b`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::CreateLicenseDom`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7a80`

## callees

- `0x9900`
- `0xa010`
- `0xa100`
- `0xa240`
- `0xa250`
- `0xa270`

## string_xrefs

- `0x993a`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`
- `0x990e`: `<r:license xmlns:r="urn:mpeg:mpeg21:2003:01-REL-R-NS" xmlns:as="http://schemas.microsoft.com/windows/pki/2005/Authenticode"><r:grant><as:ManifestInformation><as:assemblyIdentity /></as:ManifestInformation><as:SignedBy/><as:AuthenticodePublisher><as:X509SubjectName>CN=dummy</as:X509SubjectName></as:AuthenticodePublisher></r:grant><r:issuer></r:issuer></r:license>`
- `0x9945`: `r:license/r:grant/as:ManifestInformation/as:assemblyIdentity`
- `0x99ae`: `r:license/r:grant/as:ManifestInformation`

## pseudocode

```c

```

## disassembly

```asm
0x9900  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x9905  stloc.0
0x9906  ldloc.0
0x9907  ldc.i4.1
0x9908  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_PreserveWhitespace(bool)
0x990d  ldloc.0
0x990e  ldstr    aRLicenseXmlnsR// "<r:license xmlns:r=\"urn:mpeg:mpeg21:20"...
0x9913  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x9918  ldloc.0
0x9919  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x991e  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x9923  stloc.1
0x9924  ldloc.1
0x9925  ldstr    aR// "r"
0x992a  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x992f  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9934  ldloc.1
0x9935  ldstr    aAs// "as"
0x993a  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x993f  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9944  ldloc.0
0x9945  ldstr    aRLicenseRGrant// "r:license/r:grant/as:ManifestInformatio"...
0x994a  ldloc.1
0x994b  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9950  isinst   [System.Xml]System.Xml.XmlElement
0x9955  stloc.2
0x9956  ldloc.2
0x9957  callvirt instance void [System.Xml]System.Xml.XmlElement::RemoveAllAttributes()
0x995c  ldarg.1
0x995d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x9962  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNamedNodeMap::GetEnumerator()
0x9967  stloc.s  5
0x9969  br.s     loc_998D
0x996b  ldloc.s  5
0x996d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9972  castclass [System.Xml]System.Xml.XmlAttribute
0x9977  stloc.s  6
0x9979  ldloc.2
0x997a  ldloc.s  6
0x997c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x9981  ldloc.s  6
0x9983  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x9988  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x998d  ldloc.s  5
0x998f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9994  brtrue.s loc_996B
0x9996  leave.s  loc_99AD
0x9998  ldloc.s  5
0x999a  isinst   [mscorlib]System.IDisposable
0x999f  stloc.s  7
0x99a1  ldloc.s  7
0x99a3  brfalse.s loc_99AC
0x99a5  ldloc.s  7
0x99a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x99ac  endfinally
0x99ad  ldloc.0
0x99ae  ldstr    aRLicenseRGrant_0// "r:license/r:grant/as:ManifestInformatio"...
0x99b3  ldloc.1
0x99b4  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x99b9  isinst   [System.Xml]System.Xml.XmlElement
0x99be  stloc.3
0x99bf  ldloc.3
0x99c0  ldstr    aHash// "Hash"
0x99c5  ldarg.2
0x99c6  ldlen
0x99c7  brfalse.s loc_99D5
0x99c9  ldarg.2
0x99ca  ldc.i4.0
0x99cb  ldarg.2
0x99cc  ldlen
0x99cd  conv.i4
0x99ce  call     string System.Deployment.Internal.CodeSigning.SignedCmiManifest2::BytesToHexString(unsigned int8[] array, int32 start, int32 end)
0x99d3  br.s     loc_99DA
0x99d5  ldstr    asc_2F208// ""
0x99da  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x99df  ldloc.3
0x99e0  ldstr    aDescription// "Description"
0x99e5  ldarg.0
0x99e6  callvirt instance string System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_Description()
0x99eb  brfalse.s loc_99F5
0x99ed  ldarg.0
0x99ee  callvirt instance string System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_Description()
0x99f3  br.s     loc_99FA
0x99f5  ldstr    asc_2F208// ""
0x99fa  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x99ff  ldloc.3
0x9a00  ldstr    aUrl// "Url"
0x9a05  ldarg.0
0x9a06  callvirt instance string System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_DescriptionUrl()
0x9a0b  brfalse.s loc_9A15
0x9a0d  ldarg.0
0x9a0e  callvirt instance string System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_DescriptionUrl()
0x9a13  br.s     loc_9A1A
0x9a15  ldstr    asc_2F208// ""
0x9a1a  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x9a1f  ldloc.0
0x9a20  ldstr    aRLicenseRGrant_1// "r:license/r:grant/as:AuthenticodePublis"...
0x9a25  ldloc.1
0x9a26  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9a2b  isinst   [System.Xml]System.Xml.XmlElement
0x9a30  stloc.s  4
0x9a32  ldloc.s  4
0x9a34  ldarg.0
0x9a35  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 System.Deployment.Internal.CodeSigning.CmiManifestSigner2::get_Certificate()
0x9a3a  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x9a3f  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x9a44  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x9a49  ldloc.0
0x9a4a  ret
```
