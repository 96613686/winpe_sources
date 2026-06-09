# System.Deployment.Application.ManifestGenerator::GetNamespaceMgr

- ea: `0x192f0`
- end: `0x1932e`
- name: `System.Deployment.Application.ManifestGenerator::GetNamespaceMgr`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19040`
- `0x190c0`

## string_xrefs

- `0x19322`: `http://www.w3.org/2000/09/xmldsig#`
- `0x19302`: `urn:schemas-microsoft-com:asm.v1`
- `0x19312`: `urn:schemas-microsoft-com:asm.v2`

## pseudocode

```c

```

## disassembly

```asm
0x192f0  ldarg.0
0x192f1  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x192f6  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x192fb  stloc.0
0x192fc  ldloc.0
0x192fd  ldstr    aAsmv1// "asmv1"
0x19302  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x19307  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x1930c  ldloc.0
0x1930d  ldstr    aAsmv2// "asmv2"
0x19312  ldstr    aUrnSchemasMicr_0// "urn:schemas-microsoft-com:asm.v2"
0x19317  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x1931c  ldloc.0
0x1931d  ldstr    aDsig// "dsig"
0x19322  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x19327  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x1932c  ldloc.0
0x1932d  ret
```
