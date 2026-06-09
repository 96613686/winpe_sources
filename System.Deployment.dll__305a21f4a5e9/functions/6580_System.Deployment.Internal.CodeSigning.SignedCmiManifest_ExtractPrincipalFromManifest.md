# System.Deployment.Internal.CodeSigning.SignedCmiManifest::ExtractPrincipalFromManifest

- ea: `0x6580`
- end: `0x65c8`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::ExtractPrincipalFromManifest`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60b0`

## callees

- `0x6580`

## string_xrefs

- `0x6597`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x6580  ldarg.0
0x6581  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6586  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x658b  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x6590  stloc.0
0x6591  ldloc.0
0x6592  ldstr    aAsm// "asm"
0x6597  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x659c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x65a1  ldarg.0
0x65a2  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x65a7  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x65ac  ldloc.0
0x65ad  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x65b2  stloc.1
0x65b3  ldloc.1
0x65b4  brtrue.s loc_65C1
0x65b6  ldc.i4   0x800B0003
0x65bb  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x65c0  throw
0x65c1  ldloc.1
0x65c2  isinst   [System.Xml]System.Xml.XmlElement
0x65c7  ret
```
