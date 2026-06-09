# System.Deployment.Internal.CodeSigning.SignedCmiManifest::InsertPublisherIdentity

- ea: `0x6a80`
- end: `0x6b9c`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::InsertPublisherIdentity`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60b0`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5ef0`
- `0x6a80`

## string_xrefs

- `0x6ab2`: `http://www.w3.org/2000/09/xmldsig#`
- `0x6a92`: `urn:schemas-microsoft-com:asm.v1`
- `0x6aa2`: `urn:schemas-microsoft-com:asm.v2`
- `0x6b09`: `urn:schemas-microsoft-com:asm.v2`

## pseudocode

```c

```

## disassembly

```asm
0x6a80  ldarg.0
0x6a81  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x6a86  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x6a8b  stloc.0
0x6a8c  ldloc.0
0x6a8d  ldstr    aAsm// "asm"
0x6a92  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x6a97  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6a9c  ldloc.0
0x6a9d  ldstr    aAsm2// "asm2"
0x6aa2  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x6aa7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6aac  ldloc.0
0x6aad  ldstr    aDs// "ds"
0x6ab2  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x6ab7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6abc  ldarg.0
0x6abd  ldstr    aAsmAssembly// "asm:assembly"
0x6ac2  ldloc.0
0x6ac3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6ac8  isinst   [System.Xml]System.Xml.XmlElement
0x6acd  stloc.1
0x6ace  ldarg.0
0x6acf  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x6ad4  ldloc.0
0x6ad5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6ada  isinst   [System.Xml]System.Xml.XmlElement
0x6adf  stloc.2
0x6ae0  ldloc.2
0x6ae1  brtrue.s loc_6AEE
0x6ae3  ldc.i4   0x800B0003
0x6ae8  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6aed  throw
0x6aee  ldarg.0
0x6aef  ldstr    aAsmAssemblyAsm_0// "asm:assembly/asm2:publisherIdentity"
0x6af4  ldloc.0
0x6af5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6afa  isinst   [System.Xml]System.Xml.XmlElement
0x6aff  stloc.3
0x6b00  ldloc.3
0x6b01  brtrue.s loc_6B14
0x6b03  ldarg.0
0x6b04  ldstr    aPublisherident// "publisherIdentity"
0x6b09  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x6b0e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x6b13  stloc.3
0x6b14  ldloca.s 4
0x6b16  initobj  [mscorlib]System.IntPtr
0x6b1c  ldarg.1
0x6b1d  callvirt instance native int [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Handle()
0x6b22  ldloca.s 4
0x6b24  call     int32 System.Deployment.Internal.CodeSigning.Win32::_AxlGetIssuerPublicKeyHash([in] native int pCertContext, [in] [out] native int& ppwszPublicKeyHash)
0x6b29  stloc.s  5
0x6b2b  ldloc.s  5
0x6b2d  brfalse.s loc_6B37
0x6b2f  ldloc.s  5
0x6b31  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6b36  throw
0x6b37  ldloc.s  4
0x6b39  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x6b3e  stloc.s  6
0x6b40  call     native int System.Deployment.Internal.CodeSigning.Win32::GetProcessHeap()
0x6b45  ldc.i4.0
0x6b46  ldloc.s  4
0x6b48  call     bool System.Deployment.Internal.CodeSigning.Win32::HeapFree([hasfieldmarshal] native int, [in] unsigned int32 hHeap, [in] native int dwFlags)
0x6b4d  pop
0x6b4e  ldloc.3
0x6b4f  ldstr    aName// "name"
0x6b54  ldarg.1
0x6b55  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x6b5a  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x6b5f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6b64  ldloc.3
0x6b65  ldstr    aIssuerkeyhash// "issuerKeyHash"
0x6b6a  ldloc.s  6
0x6b6c  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6b71  ldarg.0
0x6b72  ldstr    aAsmAssemblyDsS_2// "asm:assembly/ds:Signature"
0x6b77  ldloc.0
0x6b78  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6b7d  isinst   [System.Xml]System.Xml.XmlElement
0x6b82  stloc.s  7
0x6b84  ldloc.s  7
0x6b86  brfalse.s loc_6B93
0x6b88  ldloc.1
0x6b89  ldloc.3
0x6b8a  ldloc.s  7
0x6b8c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x6b91  pop
0x6b92  ret
0x6b93  ldloc.1
0x6b94  ldloc.3
0x6b95  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6b9a  pop
0x6b9b  ret
```
