# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyLicense

- ea: `0x7c80`
- end: `0x7e5a`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyLicense`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7b40`

## callees

- `0x5ec0`
- `0x5ed0`
- `0x5ee0`
- `0x7640`
- `0x7650`
- `0x7730`
- `0x7c80`
- `0x8810`
- `0x8e10`
- `0x8fe0`
- `0x90d0`
- `0xa100`

## string_xrefs

- `0x7cb7`: `http://www.w3.org/2000/09/xmldsig#`
- `0x7c97`: `urn:schemas-microsoft-com:asm.v1`
- `0x7ca7`: `urn:schemas-microsoft-com:asm.v2`
- `0x7cc7`: `http://schemas.microsoft.com/windows/rel/2005/reldata`
- `0x7ce7`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`

## pseudocode

```c

```

## disassembly

```asm
0x7c80  ldarg.0
0x7c81  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7c86  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x7c8b  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x7c90  stloc.0
0x7c91  ldloc.0
0x7c92  ldstr    aAsm// "asm"
0x7c97  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x7c9c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7ca1  ldloc.0
0x7ca2  ldstr    aAsm2// "asm2"
0x7ca7  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x7cac  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7cb1  ldloc.0
0x7cb2  ldstr    aDs// "ds"
0x7cb7  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x7cbc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7cc1  ldloc.0
0x7cc2  ldstr    aMsrel// "msrel"
0x7cc7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/windows/re"...
0x7ccc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7cd1  ldloc.0
0x7cd2  ldstr    aR// "r"
0x7cd7  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x7cdc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7ce1  ldloc.0
0x7ce2  ldstr    aAs// "as"
0x7ce7  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x7cec  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x7cf1  ldarg.0
0x7cf2  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x7cf7  ldstr    aAsmAssemblyDsS// "asm:assembly/ds:Signature/ds:KeyInfo/ms"...
0x7cfc  ldloc.0
0x7cfd  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x7d02  isinst   [System.Xml]System.Xml.XmlElement
0x7d07  stloc.1
0x7d08  ldloc.1
0x7d09  brtrue.s loc_7D0C
0x7d0b  ret
0x7d0c  ldarg.0
0x7d0d  ldloc.0
0x7d0e  call     instance bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::OverrideTimestampImprovements(class [System.Xml]System.Xml.XmlNamespaceManager nsm)
0x7d13  brtrue.s loc_7D5F
0x7d15  ldloc.1
0x7d16  ldstr    aRIssuerDsSigna// "r:issuer/ds:Signature"
0x7d1b  ldloc.0
0x7d1c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x7d21  stloc.2
0x7d22  ldloc.2
0x7d23  brfalse.s loc_7D2E
0x7d25  ldloc.2
0x7d26  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x7d2b  ldc.i4.1
0x7d2c  beq.s    loc_7D49
0x7d2e  ldarg.0
0x7d2f  ldfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7d34  ldc.i4   0x800B0100
0x7d39  callvirt instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::set_ErrorCode(int32 value)
0x7d3e  ldc.i4   0x800B0100
0x7d43  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x7d48  throw
0x7d49  ldarg.0
0x7d4a  ldloc.2
0x7d4b  ldc.i4.0
0x7d4c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x7d51  isinst   [System.Xml]System.Xml.XmlElement
0x7d56  ldloc.0
0x7d57  ldloca.s 3
0x7d59  call     instance bool System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureTimestampNew(class [System.Xml]System.Xml.XmlElement signatureNode, class [System.Xml]System.Xml.XmlNamespaceManager nsm, [out] valuetype [mscorlib]System.DateTime& verificationTime)
0x7d5e  pop
0x7d5f  ldarg.0
0x7d60  ldloc.0
0x7d61  ldc.i4.0
0x7d62  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyAssemblyIdentity(class [System.Xml]System.Xml.XmlNamespaceManager nsm, valuetype System.Deployment.Internal.CodeSigning.SupportedHashAlgorithm hashAlgorithm)
0x7d67  ldarg.0
0x7d68  ldc.i4   0x800B010B
0x7d6d  newobj   instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::.ctor(int32 errorCode)
0x7d72  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7d77  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x7d7c  ldloc.1
0x7d7d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x7d82  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x7d87  stloc.s  4
0x7d89  ldloc.s  4
0x7d8b  dup
0x7d8c  stloc.s  6
0x7d8e  brfalse.s loc_7D96
0x7d90  ldloc.s  6
0x7d92  ldlen
0x7d93  conv.i4
0x7d94  brtrue.s loc_7D9C
0x7d96  ldc.i4.0
0x7d97  conv.u
0x7d98  stloc.s  5
0x7d9a  br.s     loc_7DA7
0x7d9c  ldloc.s  6
0x7d9e  ldc.i4.0
0x7d9f  ldelema  [mscorlib]System.Byte
0x7da4  conv.u
0x7da5  stloc.s  5
0x7da7  ldloca.s 7
0x7da9  initobj  AXL_SIGNER_INFO
0x7daf  ldloca.s 7
0x7db1  ldtoken  AXL_SIGNER_INFO
0x7db6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7dbb  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x7dc0  stfld    unsigned int32 AXL_SIGNER_INFO::cbSize
0x7dc5  ldloca.s 8
0x7dc7  initobj  AXL_TIMESTAMPER_INFO
0x7dcd  ldloca.s 8
0x7dcf  ldtoken  AXL_TIMESTAMPER_INFO
0x7dd4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7dd9  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x7dde  stfld    unsigned int32 AXL_TIMESTAMPER_INFO::cbSize
0x7de3  ldloca.s 9
0x7de5  initobj  CRYPT_DATA_BLOB
0x7deb  ldloca.s 0xA
0x7ded  ldloc.s  5
0x7def  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x7df4  ldloca.s 9
0x7df6  ldloc.s  4
0x7df8  ldlen
0x7df9  conv.i4
0x7dfa  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x7dff  ldloca.s 9
0x7e01  ldloc.s  0xA
0x7e03  stfld    native int CRYPT_DATA_BLOB::pbData
0x7e08  ldloca.s 9
0x7e0a  ldarg.1
0x7e0b  ldloca.s 7
0x7e0d  ldloca.s 8
0x7e0f  call     int32 System.Deployment.Internal.CodeSigning.Win32::CertVerifyAuthenticodeLicense([in] valuetype CRYPT_DATA_BLOB& pLicenseBlob, [in] unsigned int32 dwFlags, [in] [out] valuetype AXL_SIGNER_INFO& pSignerInfo, [in] [out] valuetype AXL_TIMESTAMPER_INFO& pTimestamperInfo)
0x7e14  stloc.s  0xB
0x7e16  ldc.i4   0x800B0100
0x7e1b  ldloc.s  7
0x7e1d  ldfld    unsigned int32 AXL_SIGNER_INFO::dwError
0x7e22  beq.s    loc_7E33
0x7e24  ldarg.0
0x7e25  ldloc.s  7
0x7e27  ldloc.s  8
0x7e29  newobj   instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::.ctor(valuetype AXL_SIGNER_INFO signerInfo, valuetype AXL_TIMESTAMPER_INFO timestamperInfo)
0x7e2e  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_authenticodeSignerInfo
0x7e33  ldloca.s 7
0x7e35  call     int32 System.Deployment.Internal.CodeSigning.Win32::CertFreeAuthenticodeSignerInfo([in] valuetype AXL_SIGNER_INFO& pSignerInfo)
0x7e3a  pop
0x7e3b  ldloca.s 8
0x7e3d  call     int32 System.Deployment.Internal.CodeSigning.Win32::CertFreeAuthenticodeTimestamperInfo([in] valuetype AXL_TIMESTAMPER_INFO& pTimestamperInfo)
0x7e42  pop
0x7e43  ldloc.s  0xB
0x7e45  brfalse.s loc_7E4F
0x7e47  ldloc.s  0xB
0x7e49  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x7e4e  throw
0x7e4f  ldnull
0x7e50  stloc.s  6
0x7e52  ldarg.0
0x7e53  ldloc.0
0x7e54  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyPublisherIdentity(class [System.Xml]System.Xml.XmlNamespaceManager nsm)
0x7e59  ret
```
