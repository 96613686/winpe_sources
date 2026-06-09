# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::TimestampSignedLicenseDom

- ea: `0x9d20`
- end: `0x9e9c`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::TimestampSignedLicenseDom`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9a50`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5eb0`
- `0x9bb0`
- `0x9d20`
- `0xa100`

## string_xrefs

- `0x9d42`: `http://www.w3.org/2000/09/xmldsig#`
- `0x9e6c`: `http://www.w3.org/2000/09/xmldsig#`
- `0x9d52`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`
- `0x9e54`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`

## pseudocode

```c

```

## disassembly

```asm
0x9d20  ldarg.0
0x9d21  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x9d26  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x9d2b  stloc.0
0x9d2c  ldloc.0
0x9d2d  ldstr    aR// "r"
0x9d32  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x9d37  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9d3c  ldloc.0
0x9d3d  ldstr    aDs// "ds"
0x9d42  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x9d47  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9d4c  ldloc.0
0x9d4d  ldstr    aAs// "as"
0x9d52  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x9d57  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9d5c  ldsfld   string [mscorlib]System.String::Empty
0x9d61  stloc.1
0x9d62  ldarg.0
0x9d63  ldstr    aRLicenseRIssue_1// "r:license/r:issuer/ds:Signature/ds:Sign"...
0x9d68  ldloc.0
0x9d69  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9d6e  isinst   [System.Xml]System.Xml.XmlElement
0x9d73  stloc.s  5
0x9d75  ldloc.s  5
0x9d77  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x9d7c  stloc.s  6
0x9d7e  ldarg.1
0x9d7f  ldloc.s  6
0x9d81  ldarg.2
0x9d82  call     string System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ObtainRFC3161Timestamp(string timeStampUrl, string signatureValue, bool useSha256)
0x9d87  stloc.1
0x9d88  leave    loc_9E49
0x9d8d  pop
0x9d8e  ldloca.s 7
0x9d90  initobj  CRYPT_DATA_BLOB
0x9d96  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x9d9b  ldarg.0
0x9d9c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x9da1  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x9da6  stloc.s  8
0x9da8  ldloc.s  8
0x9daa  dup
0x9dab  stloc.s  0xB
0x9dad  brfalse.s loc_9DB5
0x9daf  ldloc.s  0xB
0x9db1  ldlen
0x9db2  conv.i4
0x9db3  brtrue.s loc_9DBB
0x9db5  ldc.i4.0
0x9db6  conv.u
0x9db7  stloc.s  0xA
0x9db9  br.s     loc_9DC6
0x9dbb  ldloc.s  0xB
0x9dbd  ldc.i4.0
0x9dbe  ldelema  [mscorlib]System.Byte
0x9dc3  conv.u
0x9dc4  stloc.s  0xA
0x9dc6  ldloca.s 0xC
0x9dc8  initobj  CRYPT_DATA_BLOB
0x9dce  ldloca.s 0xD
0x9dd0  ldloc.s  0xA
0x9dd2  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x9dd7  ldloca.s 0xC
0x9dd9  ldloc.s  8
0x9ddb  ldlen
0x9ddc  conv.i4
0x9ddd  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x9de2  ldloca.s 0xC
0x9de4  ldloc.s  0xD
0x9de6  stfld    native int CRYPT_DATA_BLOB::pbData
0x9deb  ldloca.s 0xC
0x9ded  ldarg.1
0x9dee  ldloca.s 7
0x9df0  call     int32 System.Deployment.Internal.CodeSigning.Win32::CertTimestampAuthenticodeLicense([in] valuetype CRYPT_DATA_BLOB& pSignedLicenseBlob, [in] string pwszTimestampURI, [in] [out] valuetype CRYPT_DATA_BLOB& pTimestampSignatureBlob)
0x9df5  stloc.s  0xE
0x9df7  ldloc.s  0xE
0x9df9  brfalse.s loc_9E03
0x9dfb  ldloc.s  0xE
0x9dfd  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9e02  throw
0x9e03  ldnull
0x9e04  stloc.s  0xB
0x9e06  ldloc.s  7
0x9e08  ldfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x9e0d  newarr   [mscorlib]System.Byte
0x9e12  stloc.s  9
0x9e14  ldloc.s  7
0x9e16  ldfld    native int CRYPT_DATA_BLOB::pbData
0x9e1b  ldloc.s  9
0x9e1d  ldc.i4.0
0x9e1e  ldloc.s  9
0x9e20  ldlen
0x9e21  conv.i4
0x9e22  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x9e27  call     native int System.Deployment.Internal.CodeSigning.Win32::GetProcessHeap()
0x9e2c  ldc.i4.0
0x9e2d  ldloc.s  7
0x9e2f  ldfld    native int CRYPT_DATA_BLOB::pbData
0x9e34  call     bool System.Deployment.Internal.CodeSigning.Win32::HeapFree([hasfieldmarshal] native int, [in] unsigned int32 hHeap, [in] native int dwFlags)
0x9e39  pop
0x9e3a  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x9e3f  ldloc.s  9
0x9e41  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x9e46  stloc.1
0x9e47  leave.s  loc_9E49
0x9e49  ldarg.0
0x9e4a  ldstr    aAs// "as"
0x9e4f  ldstr    aTimestamp// "Timestamp"
0x9e54  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x9e59  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x9e5e  stloc.2
0x9e5f  ldloc.2
0x9e60  ldloc.1
0x9e61  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x9e66  ldarg.0
0x9e67  ldstr    aObject// "Object"
0x9e6c  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x9e71  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x9e76  stloc.3
0x9e77  ldloc.3
0x9e78  ldloc.2
0x9e79  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x9e7e  pop
0x9e7f  ldarg.0
0x9e80  ldstr    aRLicenseRIssue_0// "r:license/r:issuer/ds:Signature"
0x9e85  ldloc.0
0x9e86  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9e8b  isinst   [System.Xml]System.Xml.XmlElement
0x9e90  stloc.s  4
0x9e92  ldloc.s  4
0x9e94  ldloc.3
0x9e95  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x9e9a  pop
0x9e9b  ret
```
