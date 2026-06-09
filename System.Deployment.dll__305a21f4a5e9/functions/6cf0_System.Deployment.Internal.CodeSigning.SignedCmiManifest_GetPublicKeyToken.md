# System.Deployment.Internal.CodeSigning.SignedCmiManifest::GetPublicKeyToken

- ea: `0x6cf0`
- end: `0x6d55`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::GetPublicKeyToken`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x68d0`

## callees

- `0x6cf0`

## string_xrefs

- `0x6d12`: `http://www.w3.org/2000/09/xmldsig#`
- `0x6d02`: `urn:schemas-microsoft-com:asm.v1`
- `0x6d32`: `publicKeyToken`
- `0x6d4a`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0x6cf0  ldarg.0
0x6cf1  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x6cf6  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x6cfb  stloc.0
0x6cfc  ldloc.0
0x6cfd  ldstr    aAsm// "asm"
0x6d02  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x6d07  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6d0c  ldloc.0
0x6d0d  ldstr    aDs// "ds"
0x6d12  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x6d17  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6d1c  ldarg.0
0x6d1d  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x6d22  ldloc.0
0x6d23  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6d28  isinst   [System.Xml]System.Xml.XmlElement
0x6d2d  stloc.1
0x6d2e  ldloc.1
0x6d2f  brfalse.s loc_6D3E
0x6d31  ldloc.1
0x6d32  ldstr    aPublickeytoken// "publicKeyToken"
0x6d37  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x6d3c  brtrue.s loc_6D49
0x6d3e  ldc.i4   0x800B0003
0x6d43  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6d48  throw
0x6d49  ldloc.1
0x6d4a  ldstr    aPublickeytoken// "publicKeyToken"
0x6d4f  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x6d54  ret
```
