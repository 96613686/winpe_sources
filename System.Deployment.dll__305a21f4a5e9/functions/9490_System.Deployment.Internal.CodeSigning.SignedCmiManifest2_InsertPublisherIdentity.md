# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::InsertPublisherIdentity

- ea: `0x9490`
- end: `0x95ac`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::InsertPublisherIdentity`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7a80`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5ef0`
- `0x9490`
- `0xa100`

## string_xrefs

- `0x94c2`: `http://www.w3.org/2000/09/xmldsig#`
- `0x94a2`: `urn:schemas-microsoft-com:asm.v1`
- `0x94b2`: `urn:schemas-microsoft-com:asm.v2`
- `0x9519`: `urn:schemas-microsoft-com:asm.v2`

## pseudocode

```c

```

## disassembly

```asm
0x9490  ldarg.0
0x9491  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x9496  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x949b  stloc.0
0x949c  ldloc.0
0x949d  ldstr    aAsm// "asm"
0x94a2  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x94a7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x94ac  ldloc.0
0x94ad  ldstr    aAsm2// "asm2"
0x94b2  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x94b7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x94bc  ldloc.0
0x94bd  ldstr    aDs// "ds"
0x94c2  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x94c7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x94cc  ldarg.0
0x94cd  ldstr    aAsmAssembly// "asm:assembly"
0x94d2  ldloc.0
0x94d3  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x94d8  isinst   [System.Xml]System.Xml.XmlElement
0x94dd  stloc.1
0x94de  ldarg.0
0x94df  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x94e4  ldloc.0
0x94e5  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x94ea  isinst   [System.Xml]System.Xml.XmlElement
0x94ef  stloc.2
0x94f0  ldloc.2
0x94f1  brtrue.s loc_94FE
0x94f3  ldc.i4   0x800B0003
0x94f8  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x94fd  throw
0x94fe  ldarg.0
0x94ff  ldstr    aAsmAssemblyAsm_0// "asm:assembly/asm2:publisherIdentity"
0x9504  ldloc.0
0x9505  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x950a  isinst   [System.Xml]System.Xml.XmlElement
0x950f  stloc.3
0x9510  ldloc.3
0x9511  brtrue.s loc_9524
0x9513  ldarg.0
0x9514  ldstr    aPublisherident// "publisherIdentity"
0x9519  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x951e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x9523  stloc.3
0x9524  ldloca.s 4
0x9526  initobj  [mscorlib]System.IntPtr
0x952c  ldarg.1
0x952d  callvirt instance native int [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Handle()
0x9532  ldloca.s 4
0x9534  call     int32 System.Deployment.Internal.CodeSigning.Win32::_AxlGetIssuerPublicKeyHash([in] native int pCertContext, [in] [out] native int& ppwszPublicKeyHash)
0x9539  stloc.s  5
0x953b  ldloc.s  5
0x953d  brfalse.s loc_9547
0x953f  ldloc.s  5
0x9541  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9546  throw
0x9547  ldloc.s  4
0x9549  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x954e  stloc.s  6
0x9550  call     native int System.Deployment.Internal.CodeSigning.Win32::GetProcessHeap()
0x9555  ldc.i4.0
0x9556  ldloc.s  4
0x9558  call     bool System.Deployment.Internal.CodeSigning.Win32::HeapFree([hasfieldmarshal] native int, [in] unsigned int32 hHeap, [in] native int dwFlags)
0x955d  pop
0x955e  ldloc.3
0x955f  ldstr    aName// "name"
0x9564  ldarg.1
0x9565  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x956a  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x956f  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x9574  ldloc.3
0x9575  ldstr    aIssuerkeyhash// "issuerKeyHash"
0x957a  ldloc.s  6
0x957c  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x9581  ldarg.0
0x9582  ldstr    aAsmAssemblyDsS_2// "asm:assembly/ds:Signature"
0x9587  ldloc.0
0x9588  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x958d  isinst   [System.Xml]System.Xml.XmlElement
0x9592  stloc.s  7
0x9594  ldloc.s  7
0x9596  brfalse.s loc_95A3
0x9598  ldloc.1
0x9599  ldloc.3
0x959a  ldloc.s  7
0x959c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0x95a1  pop
0x95a2  ret
0x95a3  ldloc.1
0x95a4  ldloc.3
0x95a5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x95aa  pop
0x95ab  ret
```
