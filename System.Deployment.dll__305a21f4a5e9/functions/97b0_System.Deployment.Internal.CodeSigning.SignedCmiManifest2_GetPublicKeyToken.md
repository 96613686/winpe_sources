# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetPublicKeyToken

- ea: `0x97b0`
- end: `0x9815`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetPublicKeyToken`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x92e0`

## callees

- `0x97b0`
- `0xa100`

## string_xrefs

- `0x97d2`: `http://www.w3.org/2000/09/xmldsig#`
- `0x97c2`: `urn:schemas-microsoft-com:asm.v1`
- `0x97f2`: `publicKeyToken`
- `0x980a`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0x97b0  ldarg.0
0x97b1  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x97b6  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x97bb  stloc.0
0x97bc  ldloc.0
0x97bd  ldstr    aAsm// "asm"
0x97c2  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x97c7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x97cc  ldloc.0
0x97cd  ldstr    aDs// "ds"
0x97d2  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x97d7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x97dc  ldarg.0
0x97dd  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x97e2  ldloc.0
0x97e3  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x97e8  isinst   [System.Xml]System.Xml.XmlElement
0x97ed  stloc.1
0x97ee  ldloc.1
0x97ef  brfalse.s loc_97FE
0x97f1  ldloc.1
0x97f2  ldstr    aPublickeytoken// "publicKeyToken"
0x97f7  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x97fc  brtrue.s loc_9809
0x97fe  ldc.i4   0x800B0003
0x9803  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9808  throw
0x9809  ldloc.1
0x980a  ldstr    aPublickeytoken// "publicKeyToken"
0x980f  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x9814  ret
```
