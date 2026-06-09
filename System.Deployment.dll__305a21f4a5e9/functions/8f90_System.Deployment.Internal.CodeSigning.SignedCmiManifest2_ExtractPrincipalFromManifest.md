# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ExtractPrincipalFromManifest

- ea: `0x8f90`
- end: `0x8fd8`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ExtractPrincipalFromManifest`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7a80`

## callees

- `0x8f90`
- `0xa100`

## string_xrefs

- `0x8fa7`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x8f90  ldarg.0
0x8f91  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x8f96  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x8f9b  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x8fa0  stloc.0
0x8fa1  ldloc.0
0x8fa2  ldstr    aAsm// "asm"
0x8fa7  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x8fac  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x8fb1  ldarg.0
0x8fb2  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x8fb7  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x8fbc  ldloc.0
0x8fbd  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x8fc2  stloc.1
0x8fc3  ldloc.1
0x8fc4  brtrue.s loc_8FD1
0x8fc6  ldc.i4   0x800B0003
0x8fcb  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x8fd0  throw
0x8fd1  ldloc.1
0x8fd2  isinst   [System.Xml]System.Xml.XmlElement
0x8fd7  ret
```
