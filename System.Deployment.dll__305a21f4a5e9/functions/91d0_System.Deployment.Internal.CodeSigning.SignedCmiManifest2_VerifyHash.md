# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyHash

- ea: `0x91d0`
- end: `0x92d5`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyHash`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x8fe0`

## callees

- `0x91d0`
- `0x9820`
- `0xa070`
- `0xa100`

## string_xrefs

- `0x91ef`: `asm:assembly/ds:Signature/ds:KeyInfo/msrel:RelData/r:license/r:grant/as:ManifestInformation`

## pseudocode

```c

```

## disassembly

```asm
0x91d0  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x91d5  stloc.0
0x91d6  ldloc.0
0x91d7  ldc.i4.1
0x91d8  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_PreserveWhitespace(bool)
0x91dd  ldarg.0
0x91de  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x91e3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::Clone()
0x91e8  castclass [System.Xml]System.Xml.XmlDocument
0x91ed  stloc.0
0x91ee  ldloc.0
0x91ef  ldstr    aAsmAssemblyDsS_1// "asm:assembly/ds:Signature/ds:KeyInfo/ms"...
0x91f4  ldarg.1
0x91f5  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x91fa  isinst   [System.Xml]System.Xml.XmlElement
0x91ff  stloc.1
0x9200  ldloc.1
0x9201  brtrue.s loc_920E
0x9203  ldc.i4   0x800B0003
0x9208  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x920d  throw
0x920e  ldloc.1
0x920f  ldstr    aHash// "Hash"
0x9214  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x9219  brtrue.s loc_9226
0x921b  ldc.i4   0x800B0003
0x9220  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9225  throw
0x9226  ldloc.1
0x9227  ldstr    aHash// "Hash"
0x922c  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x9231  stloc.2
0x9232  ldloc.2
0x9233  brfalse.s loc_923D
0x9235  ldloc.2
0x9236  callvirt instance int32 [mscorlib]System.String::get_Length()
0x923b  brtrue.s loc_9248
0x923d  ldc.i4   0x800B0003
0x9242  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9247  throw
0x9248  ldloc.0
0x9249  ldstr    aAsmAssemblyDsS_2// "asm:assembly/ds:Signature"
0x924e  ldarg.1
0x924f  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9254  isinst   [System.Xml]System.Xml.XmlElement
0x9259  stloc.3
0x925a  ldloc.3
0x925b  brtrue.s loc_9268
0x925d  ldc.i4   0x800B0003
0x9262  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9267  throw
0x9268  ldloc.3
0x9269  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x926e  ldloc.3
0x926f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x9274  pop
0x9275  ldloc.1
0x9276  ldstr    aHash// "Hash"
0x927b  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x9280  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest2::HexStringToBytes(string hexString)
0x9285  stloc.s  4
0x9287  ldloc.0
0x9288  ldarg.2
0x9289  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ComputeHashFromManifest(class [System.Xml]System.Xml.XmlDocument manifestDom, valuetype System.Deployment.Internal.CodeSigning.SupportedHashAlgorithm supportedHashAlgorithm)
0x928e  stloc.s  5
0x9290  ldloc.s  4
0x9292  ldlen
0x9293  brfalse.s loc_929F
0x9295  ldloc.s  4
0x9297  ldlen
0x9298  conv.i4
0x9299  ldloc.s  5
0x929b  ldlen
0x929c  conv.i4
0x929d  beq.s    loc_92AA
0x929f  ldc.i4   0x80096010
0x92a4  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x92a9  throw
0x92aa  ldc.i4.0
0x92ab  stloc.s  6
0x92ad  br.s     loc_92CC
0x92af  ldloc.s  4
0x92b1  ldloc.s  6
0x92b3  ldelem.u1
0x92b4  ldloc.s  5
0x92b6  ldloc.s  6
0x92b8  ldelem.u1
0x92b9  beq.s    loc_92C6
0x92bb  ldc.i4   0x80096010
0x92c0  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x92c5  throw
0x92c6  ldloc.s  6
0x92c8  ldc.i4.1
0x92c9  add
0x92ca  stloc.s  6
0x92cc  ldloc.s  6
0x92ce  ldloc.s  4
0x92d0  ldlen
0x92d1  conv.i4
0x92d2  blt.s    loc_92AF
0x92d4  ret
```
