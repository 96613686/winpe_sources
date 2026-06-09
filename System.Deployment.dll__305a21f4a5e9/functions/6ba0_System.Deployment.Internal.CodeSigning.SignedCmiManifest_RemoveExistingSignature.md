# System.Deployment.Internal.CodeSigning.SignedCmiManifest::RemoveExistingSignature

- ea: `0x6ba0`
- end: `0x6bea`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::RemoveExistingSignature`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60b0`

## callees

- `0x6ba0`

## string_xrefs

- `0x6bc2`: `http://www.w3.org/2000/09/xmldsig#`
- `0x6bb2`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x6ba0  ldarg.0
0x6ba1  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x6ba6  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x6bab  stloc.0
0x6bac  ldloc.0
0x6bad  ldstr    aAsm// "asm"
0x6bb2  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x6bb7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6bbc  ldloc.0
0x6bbd  ldstr    aDs// "ds"
0x6bc2  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x6bc7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6bcc  ldarg.0
0x6bcd  ldstr    aAsmAssemblyDsS_2// "asm:assembly/ds:Signature"
0x6bd2  ldloc.0
0x6bd3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6bd8  stloc.1
0x6bd9  ldloc.1
0x6bda  brfalse.s loc_6BE9
0x6bdc  ldloc.1
0x6bdd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x6be2  ldloc.1
0x6be3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x6be8  pop
0x6be9  ret
```
