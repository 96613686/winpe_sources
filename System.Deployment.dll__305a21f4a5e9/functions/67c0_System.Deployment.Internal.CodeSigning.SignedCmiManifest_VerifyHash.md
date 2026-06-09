# System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyHash

- ea: `0x67c0`
- end: `0x68c4`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyHash`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x65d0`

## callees

- `0x67c0`
- `0x6d60`
- `0x7340`

## string_xrefs

- `0x67df`: `asm:assembly/ds:Signature/ds:KeyInfo/msrel:RelData/r:license/r:grant/as:ManifestInformation`

## pseudocode

```c

```

## disassembly

```asm
0x67c0  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x67c5  stloc.0
0x67c6  ldloc.0
0x67c7  ldc.i4.1
0x67c8  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_PreserveWhitespace(bool)
0x67cd  ldarg.0
0x67ce  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x67d3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::Clone()
0x67d8  castclass [System.Xml]System.Xml.XmlDocument
0x67dd  stloc.0
0x67de  ldloc.0
0x67df  ldstr    aAsmAssemblyDsS_1// "asm:assembly/ds:Signature/ds:KeyInfo/ms"...
0x67e4  ldarg.1
0x67e5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x67ea  isinst   [System.Xml]System.Xml.XmlElement
0x67ef  stloc.1
0x67f0  ldloc.1
0x67f1  brtrue.s loc_67FE
0x67f3  ldc.i4   0x800B0003
0x67f8  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x67fd  throw
0x67fe  ldloc.1
0x67ff  ldstr    aHash// "Hash"
0x6804  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x6809  brtrue.s loc_6816
0x680b  ldc.i4   0x800B0003
0x6810  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6815  throw
0x6816  ldloc.1
0x6817  ldstr    aHash// "Hash"
0x681c  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x6821  stloc.2
0x6822  ldloc.2
0x6823  brfalse.s loc_682D
0x6825  ldloc.2
0x6826  callvirt instance int32 [mscorlib]System.String::get_Length()
0x682b  brtrue.s loc_6838
0x682d  ldc.i4   0x800B0003
0x6832  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6837  throw
0x6838  ldloc.0
0x6839  ldstr    aAsmAssemblyDsS_2// "asm:assembly/ds:Signature"
0x683e  ldarg.1
0x683f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6844  isinst   [System.Xml]System.Xml.XmlElement
0x6849  stloc.3
0x684a  ldloc.3
0x684b  brtrue.s loc_6858
0x684d  ldc.i4   0x800B0003
0x6852  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6857  throw
0x6858  ldloc.3
0x6859  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x685e  ldloc.3
0x685f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x6864  pop
0x6865  ldloc.1
0x6866  ldstr    aHash// "Hash"
0x686b  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x6870  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest::HexStringToBytes(string hexString)
0x6875  stloc.s  4
0x6877  ldloc.0
0x6878  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest::ComputeHashFromManifest(class [System.Xml]System.Xml.XmlDocument manifestDom)
0x687d  stloc.s  5
0x687f  ldloc.s  4
0x6881  ldlen
0x6882  brfalse.s loc_688E
0x6884  ldloc.s  4
0x6886  ldlen
0x6887  conv.i4
0x6888  ldloc.s  5
0x688a  ldlen
0x688b  conv.i4
0x688c  beq.s    loc_6899
0x688e  ldc.i4   0x80096010
0x6893  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6898  throw
0x6899  ldc.i4.0
0x689a  stloc.s  6
0x689c  br.s     loc_68BB
0x689e  ldloc.s  4
0x68a0  ldloc.s  6
0x68a2  ldelem.u1
0x68a3  ldloc.s  5
0x68a5  ldloc.s  6
0x68a7  ldelem.u1
0x68a8  beq.s    loc_68B5
0x68aa  ldc.i4   0x80096010
0x68af  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x68b4  throw
0x68b5  ldloc.s  6
0x68b7  ldc.i4.1
0x68b8  add
0x68b9  stloc.s  6
0x68bb  ldloc.s  6
0x68bd  ldloc.s  4
0x68bf  ldlen
0x68c0  conv.i4
0x68c1  blt.s    loc_689E
0x68c3  ret
```
