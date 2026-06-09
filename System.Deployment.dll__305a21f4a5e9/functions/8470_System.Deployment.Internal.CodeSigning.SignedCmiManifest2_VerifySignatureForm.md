# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureForm

- ea: `0x8470`
- end: `0x861a`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifySignatureForm`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x7b40`
- `0x7e60`

## callees

- `0x8470`
- `0xa100`

## string_xrefs

- `0x85a5`: `http://www.w3.org/2001/10/xml-exc-c14n#`
- `0x85bf`: `http://www.w3.org/2000/09/xmldsig#enveloped-signature`

## pseudocode

```c

```

## disassembly

```asm
0x8470  ldstr    aId_2// "Id"
0x8475  stloc.0
0x8476  ldarg.1
0x8477  ldloc.0
0x8478  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x847d  brtrue.s loc_84A8
0x847f  ldstr    aId_3// "id"
0x8484  stloc.0
0x8485  ldarg.1
0x8486  ldloc.0
0x8487  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x848c  brtrue.s loc_84A8
0x848e  ldstr    aId_4// "ID"
0x8493  stloc.0
0x8494  ldarg.1
0x8495  ldloc.0
0x8496  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x849b  brtrue.s loc_84A8
0x849d  ldc.i4   0x800B0003
0x84a2  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x84a7  throw
0x84a8  ldarg.1
0x84a9  ldloc.0
0x84aa  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x84af  stloc.1
0x84b0  ldloc.1
0x84b1  brfalse.s loc_84BD
0x84b3  ldloc.1
0x84b4  ldarg.2
0x84b5  ldc.i4.4
0x84b6  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x84bb  brfalse.s loc_84C8
0x84bd  ldc.i4   0x800B0003
0x84c2  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x84c7  throw
0x84c8  ldc.i4.0
0x84c9  stloc.2
0x84ca  ldarg.1
0x84cb  ldstr    aDsSignedinfoDs// "ds:SignedInfo/ds:Reference"
0x84d0  ldarg.3
0x84d1  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x84d6  stloc.3
0x84d7  ldloc.3
0x84d8  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x84dd  stloc.s  4
0x84df  br       loc_85E8
0x84e4  ldloc.s  4
0x84e6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x84eb  castclass [System.Xml]System.Xml.XmlNode
0x84f0  stloc.s  5
0x84f2  ldloc.s  5
0x84f4  isinst   [System.Xml]System.Xml.XmlElement
0x84f9  stloc.s  6
0x84fb  ldloc.s  6
0x84fd  brfalse  loc_85E8
0x8502  ldloc.s  6
0x8504  ldstr    aUri// "URI"
0x8509  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x850e  brfalse  loc_85E8
0x8513  ldloc.s  6
0x8515  ldstr    aUri// "URI"
0x851a  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x851f  stloc.s  7
0x8521  ldloc.s  7
0x8523  brfalse  loc_85E8
0x8528  ldloc.s  7
0x852a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x852f  brtrue   loc_85E8
0x8534  ldloc.s  6
0x8536  ldstr    aDsTransforms// "ds:Transforms"
0x853b  ldarg.3
0x853c  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x8541  stloc.s  8
0x8543  ldloc.s  8
0x8545  brtrue.s loc_8552
0x8547  ldc.i4   0x800B0003
0x854c  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x8551  throw
0x8552  ldloc.s  8
0x8554  ldstr    aDsTransform// "ds:Transform"
0x8559  ldarg.3
0x855a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x855f  stloc.s  9
0x8561  ldloc.s  9
0x8563  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x8568  ldc.i4.2
0x8569  bge.s    loc_8576
0x856b  ldc.i4   0x800B0003
0x8570  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x8575  throw
0x8576  ldc.i4.0
0x8577  stloc.s  0xA
0x8579  ldc.i4.0
0x857a  stloc.s  0xB
0x857c  ldc.i4.0
0x857d  stloc.s  0xC
0x857f  br.s     loc_85DD
0x8581  ldloc.s  9
0x8583  ldloc.s  0xC
0x8585  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x858a  isinst   [System.Xml]System.Xml.XmlElement
0x858f  stloc.s  0xD
0x8591  ldloc.s  0xD
0x8593  ldstr    aAlgorithm// "Algorithm"
0x8598  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x859d  stloc.s  0xE
0x859f  ldloc.s  0xE
0x85a1  brfalse.s loc_85E8
0x85a3  ldloc.s  0xE
0x85a5  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/10/xml-exc-c14n#"
0x85aa  ldc.i4.4
0x85ab  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x85b0  brfalse.s loc_85BD
0x85b2  ldc.i4.1
0x85b3  stloc.s  0xA
0x85b5  ldloc.s  0xB
0x85b7  brfalse.s loc_85D7
0x85b9  ldc.i4.1
0x85ba  stloc.2
0x85bb  br.s     loc_85E8
0x85bd  ldloc.s  0xE
0x85bf  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2000/09/xmldsig#envel"...
0x85c4  ldc.i4.4
0x85c5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x85ca  brfalse.s loc_85D7
0x85cc  ldc.i4.1
0x85cd  stloc.s  0xB
0x85cf  ldloc.s  0xA
0x85d1  brfalse.s loc_85D7
0x85d3  ldc.i4.1
0x85d4  stloc.2
0x85d5  br.s     loc_85E8
0x85d7  ldloc.s  0xC
0x85d9  ldc.i4.1
0x85da  add
0x85db  stloc.s  0xC
0x85dd  ldloc.s  0xC
0x85df  ldloc.s  9
0x85e1  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x85e6  blt.s    loc_8581
0x85e8  ldloc.s  4
0x85ea  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x85ef  brtrue   loc_84E4
0x85f4  leave.s  loc_860B
0x85f6  ldloc.s  4
0x85f8  isinst   [mscorlib]System.IDisposable
0x85fd  stloc.s  0xF
0x85ff  ldloc.s  0xF
0x8601  brfalse.s loc_860A
0x8603  ldloc.s  0xF
0x8605  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x860a  endfinally
0x860b  ldloc.2
0x860c  brtrue.s loc_8619
0x860e  ldc.i4   0x800B0003
0x8613  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x8618  throw
0x8619  ret
```
