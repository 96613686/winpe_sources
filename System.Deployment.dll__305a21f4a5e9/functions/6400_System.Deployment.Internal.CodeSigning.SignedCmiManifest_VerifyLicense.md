# System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyLicense

- ea: `0x6400`
- end: `0x6580`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyLicense`
- size: `384`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6150`

## callees

- `0x5ec0`
- `0x5ed0`
- `0x5ee0`
- `0x6400`
- `0x65d0`
- `0x66c0`
- `0x7640`
- `0x7650`

## string_xrefs

- `0x6437`: `http://www.w3.org/2000/09/xmldsig#`
- `0x6417`: `urn:schemas-microsoft-com:asm.v1`
- `0x6427`: `urn:schemas-microsoft-com:asm.v2`
- `0x6447`: `http://schemas.microsoft.com/windows/rel/2005/reldata`
- `0x6467`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`

## pseudocode

```c

```

## disassembly

```asm
0x6400  ldarg.0
0x6401  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6406  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x640b  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x6410  stloc.0
0x6411  ldloc.0
0x6412  ldstr    aAsm// "asm"
0x6417  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x641c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6421  ldloc.0
0x6422  ldstr    aAsm2// "asm2"
0x6427  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x642c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6431  ldloc.0
0x6432  ldstr    aDs// "ds"
0x6437  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x643c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6441  ldloc.0
0x6442  ldstr    aMsrel// "msrel"
0x6447  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/windows/re"...
0x644c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6451  ldloc.0
0x6452  ldstr    aR// "r"
0x6457  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x645c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6461  ldloc.0
0x6462  ldstr    aAs// "as"
0x6467  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x646c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6471  ldarg.0
0x6472  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6477  ldstr    aAsmAssemblyDsS// "asm:assembly/ds:Signature/ds:KeyInfo/ms"...
0x647c  ldloc.0
0x647d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6482  isinst   [System.Xml]System.Xml.XmlElement
0x6487  stloc.1
0x6488  ldloc.1
0x6489  brtrue.s loc_648C
0x648b  ret
0x648c  ldarg.0
0x648d  ldloc.0
0x648e  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyAssemblyIdentity(class [System.Xml]System.Xml.XmlNamespaceManager nsm)
0x6493  ldarg.0
0x6494  ldc.i4   0x800B010B
0x6499  newobj   instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::.ctor(int32 errorCode)
0x649e  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_authenticodeSignerInfo
0x64a3  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x64a8  ldloc.1
0x64a9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x64ae  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x64b3  stloc.2
0x64b4  ldloc.2
0x64b5  dup
0x64b6  stloc.s  4
0x64b8  brfalse.s loc_64C0
0x64ba  ldloc.s  4
0x64bc  ldlen
0x64bd  conv.i4
0x64be  brtrue.s loc_64C5
0x64c0  ldc.i4.0
0x64c1  conv.u
0x64c2  stloc.3
0x64c3  br.s     loc_64CF
0x64c5  ldloc.s  4
0x64c7  ldc.i4.0
0x64c8  ldelema  [mscorlib]System.Byte
0x64cd  conv.u
0x64ce  stloc.3
0x64cf  ldloca.s 5
0x64d1  initobj  AXL_SIGNER_INFO
0x64d7  ldloca.s 5
0x64d9  ldtoken  AXL_SIGNER_INFO
0x64de  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x64e3  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x64e8  stfld    unsigned int32 AXL_SIGNER_INFO::cbSize
0x64ed  ldloca.s 6
0x64ef  initobj  AXL_TIMESTAMPER_INFO
0x64f5  ldloca.s 6
0x64f7  ldtoken  AXL_TIMESTAMPER_INFO
0x64fc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6501  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x6506  stfld    unsigned int32 AXL_TIMESTAMPER_INFO::cbSize
0x650b  ldloca.s 7
0x650d  initobj  CRYPT_DATA_BLOB
0x6513  ldloca.s 8
0x6515  ldloc.3
0x6516  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x651b  ldloca.s 7
0x651d  ldloc.2
0x651e  ldlen
0x651f  conv.i4
0x6520  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x6525  ldloca.s 7
0x6527  ldloc.s  8
0x6529  stfld    native int CRYPT_DATA_BLOB::pbData
0x652e  ldloca.s 7
0x6530  ldarg.1
0x6531  ldloca.s 5
0x6533  ldloca.s 6
0x6535  call     int32 System.Deployment.Internal.CodeSigning.Win32::CertVerifyAuthenticodeLicense([in] valuetype CRYPT_DATA_BLOB& pLicenseBlob, [in] unsigned int32 dwFlags, [in] [out] valuetype AXL_SIGNER_INFO& pSignerInfo, [in] [out] valuetype AXL_TIMESTAMPER_INFO& pTimestamperInfo)
0x653a  stloc.s  9
0x653c  ldc.i4   0x800B0100
0x6541  ldloc.s  5
0x6543  ldfld    unsigned int32 AXL_SIGNER_INFO::dwError
0x6548  beq.s    loc_6559
0x654a  ldarg.0
0x654b  ldloc.s  5
0x654d  ldloc.s  6
0x654f  newobj   instance void System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo::.ctor(valuetype AXL_SIGNER_INFO signerInfo, valuetype AXL_TIMESTAMPER_INFO timestamperInfo)
0x6554  stfld    class System.Deployment.Internal.CodeSigning.CmiAuthenticodeSignerInfo System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_authenticodeSignerInfo
0x6559  ldloca.s 5
0x655b  call     int32 System.Deployment.Internal.CodeSigning.Win32::CertFreeAuthenticodeSignerInfo([in] valuetype AXL_SIGNER_INFO& pSignerInfo)
0x6560  pop
0x6561  ldloca.s 6
0x6563  call     int32 System.Deployment.Internal.CodeSigning.Win32::CertFreeAuthenticodeTimestamperInfo([in] valuetype AXL_TIMESTAMPER_INFO& pTimestamperInfo)
0x6568  pop
0x6569  ldloc.s  9
0x656b  brfalse.s loc_6575
0x656d  ldloc.s  9
0x656f  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6574  throw
0x6575  ldnull
0x6576  stloc.s  4
0x6578  ldarg.0
0x6579  ldloc.0
0x657a  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyPublisherIdentity(class [System.Xml]System.Xml.XmlNamespaceManager nsm)
0x657f  ret
```
