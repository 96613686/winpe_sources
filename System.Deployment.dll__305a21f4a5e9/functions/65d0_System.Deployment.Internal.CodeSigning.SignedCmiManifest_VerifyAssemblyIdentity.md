# System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyAssemblyIdentity

- ea: `0x65d0`
- end: `0x66bd`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyAssemblyIdentity`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x6400`

## callees

- `0x65d0`
- `0x67c0`

## string_xrefs

- `0x65ed`: `asm:assembly/ds:Signature/ds:KeyInfo/msrel:RelData/r:license/r:grant/as:ManifestInformation/as:assemblyIdentity`

## pseudocode

```c

```

## disassembly

```asm
0x65d0  ldarg.0
0x65d1  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x65d6  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x65db  ldarg.1
0x65dc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x65e1  isinst   [System.Xml]System.Xml.XmlElement
0x65e6  stloc.0
0x65e7  ldarg.0
0x65e8  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x65ed  ldstr    aAsmAssemblyDsS_0// "asm:assembly/ds:Signature/ds:KeyInfo/ms"...
0x65f2  ldarg.1
0x65f3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x65f8  isinst   [System.Xml]System.Xml.XmlElement
0x65fd  stloc.1
0x65fe  ldloc.0
0x65ff  brfalse.s loc_6614
0x6601  ldloc.1
0x6602  brfalse.s loc_6614
0x6604  ldloc.0
0x6605  callvirt instance bool [System.Xml]System.Xml.XmlElement::get_HasAttributes()
0x660a  brfalse.s loc_6614
0x660c  ldloc.1
0x660d  callvirt instance bool [System.Xml]System.Xml.XmlElement::get_HasAttributes()
0x6612  brtrue.s loc_661F
0x6614  ldc.i4   0x800B0003
0x6619  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x661e  throw
0x661f  ldloc.0
0x6620  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6625  stloc.2
0x6626  ldloc.2
0x6627  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x662c  brfalse.s loc_6641
0x662e  ldloc.2
0x662f  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x6634  ldloc.1
0x6635  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x663a  callvirt instance int32 [System.Xml]System.Xml.XmlNamedNodeMap::get_Count()
0x663f  beq.s    loc_664C
0x6641  ldc.i4   0x800B0003
0x6646  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x664b  throw
0x664c  ldloc.2
0x664d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNamedNodeMap::GetEnumerator()
0x6652  stloc.3
0x6653  br.s     loc_6697
0x6655  ldloc.3
0x6656  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x665b  castclass [System.Xml]System.Xml.XmlAttribute
0x6660  stloc.s  4
0x6662  ldloc.1
0x6663  ldloc.s  4
0x6665  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0x666a  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x666f  brfalse.s loc_668C
0x6671  ldloc.s  4
0x6673  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6678  ldloc.1
0x6679  ldloc.s  4
0x667b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_LocalName()
0x6680  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x6685  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x668a  brfalse.s loc_6697
0x668c  ldc.i4   0x800B0003
0x6691  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6696  throw
0x6697  ldloc.3
0x6698  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x669d  brtrue.s loc_6655
0x669f  leave.s  loc_66B5
0x66a1  ldloc.3
0x66a2  isinst   [mscorlib]System.IDisposable
0x66a7  stloc.s  5
0x66a9  ldloc.s  5
0x66ab  brfalse.s loc_66B4
0x66ad  ldloc.s  5
0x66af  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66b4  endfinally
0x66b5  ldarg.0
0x66b6  ldarg.1
0x66b7  call     instance void System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyHash(class [System.Xml]System.Xml.XmlNamespaceManager nsm)
0x66bc  ret
```
