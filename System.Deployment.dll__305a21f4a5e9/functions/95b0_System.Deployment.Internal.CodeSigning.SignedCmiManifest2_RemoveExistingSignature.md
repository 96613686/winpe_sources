# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::RemoveExistingSignature

- ea: `0x95b0`
- end: `0x95fa`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::RemoveExistingSignature`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7a80`

## callees

- `0x95b0`
- `0xa100`

## string_xrefs

- `0x95d2`: `http://www.w3.org/2000/09/xmldsig#`
- `0x95c2`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x95b0  ldarg.0
0x95b1  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x95b6  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x95bb  stloc.0
0x95bc  ldloc.0
0x95bd  ldstr    aAsm// "asm"
0x95c2  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x95c7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x95cc  ldloc.0
0x95cd  ldstr    aDs// "ds"
0x95d2  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x95d7  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x95dc  ldarg.0
0x95dd  ldstr    aAsmAssemblyDsS_2// "asm:assembly/ds:Signature"
0x95e2  ldloc.0
0x95e3  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x95e8  stloc.1
0x95e9  ldloc.1
0x95ea  brfalse.s loc_95F9
0x95ec  ldloc.1
0x95ed  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x95f2  ldloc.1
0x95f3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x95f8  pop
0x95f9  ret
```
