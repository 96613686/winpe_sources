# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyAssemblyIdentity

- ea: `0x8fe0`
- end: `0x90ce`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyAssemblyIdentity`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x7c80`
- `0x7e60`

## callees

- `0x8fe0`
- `0x91d0`
- `0xa100`

## string_xrefs

- `0x8ffd`: `asm:assembly/ds:Signature/ds:KeyInfo/msrel:RelData/r:license/r:grant/as:ManifestInformation/as:assemblyIdentity`

## pseudocode

```c

```

## disassembly

```asm
0x8fe0  ldarg.0
0x8fe1  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x8fe6  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x8feb  ldarg.1
0x8fec  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x8ff1  isinst   [System.Xml]System.Xml.XmlElement
0x8ff6  stloc.0
0x8ff7  ldarg.0
0x8ff8  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x8ffd  ldstr    aAsmAssemblyDsS_0// "asm:assembly/ds:Signature/ds:KeyInfo/ms"...
0x9002  ldarg.1
0x9003  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9008  isinst   [System.Xml]System.Xml.XmlElement
0x900d  stloc.1
0x900e  ldloc.0
0x900f  brfalse.s loc_9024
0x9011  ldloc.1
0x9012  brfalse.s loc_9024
0x9014  ldloc.0
0x9015  callvirt instance bool [System.Xml]System.Xml.XmlElement::get_HasAttributes()
0x901a  brfalse.s loc_9024
0x901c  ldloc.1
0x901d  callvirt instance bool [System.Xml]System.Xml.XmlElement::get_HasAttributes()
0x9022  brtrue.s loc_902F
0x9024  ldc.i4   0x800B0003
0x9029  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x902e  throw
0x902f  ldloc.0
0x9030  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x9035  stloc.2
0x9036  ldloc.2
0x9037  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x903c  brfalse.s loc_9051
0x903e  ldloc.2
0x903f  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x9044  ldloc.1
0x9045  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x904a  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x904f  beq.s    loc_905C
0x9051  ldc.i4   0x800B0003
0x9056  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x905b  throw
0x905c  ldloc.2
0x905d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNamedNodeMap::GetEnumerator()
0x9062  stloc.3
0x9063  br.s     loc_90A7
0x9065  ldloc.3
0x9066  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x906b  castclass [System.Xml]System.Xml.XmlAttribute
0x9070  stloc.s  4
0x9072  ldloc.1
0x9073  ldloc.s  4
0x9075  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0x907a  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x907f  brfalse.s loc_909C
0x9081  ldloc.s  4
0x9083  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x9088  ldloc.1
0x9089  ldloc.s  4
0x908b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0x9090  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x9095  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x909a  brfalse.s loc_90A7
0x909c  ldc.i4   0x800B0003
0x90a1  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x90a6  throw
0x90a7  ldloc.3
0x90a8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x90ad  brtrue.s loc_9065
0x90af  leave.s  loc_90C5
0x90b1  ldloc.3
0x90b2  isinst   [mscorlib]System.IDisposable
0x90b7  stloc.s  5
0x90b9  ldloc.s  5
0x90bb  brfalse.s loc_90C4
0x90bd  ldloc.s  5
0x90bf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x90c4  endfinally
0x90c5  ldarg.0
0x90c6  ldarg.1
0x90c7  ldarg.2
0x90c8  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyHash(class [System.Xml]System.Xml.XmlNamespaceManager nsm, valuetype System.Deployment.Internal.CodeSigning.SupportedHashAlgorithm hashAlgorithm)
0x90cd  ret
```
