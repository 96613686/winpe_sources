# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetManifestInformation

- ea: `0x8620`
- end: `0x86d8`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetManifestInformation`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x7e60`

## callees

- `0x8620`
- `0xa0c0`
- `0xa100`

## string_xrefs

- `0x8638`: `r:grant/as:ManifestInformation`

## pseudocode

```c

```

## disassembly

```asm
0x8620  ldarg.3
0x8621  ldstr    asc_2F208// ""
0x8626  stind.ref
0x8627  ldarg.s  4
0x8629  ldstr    asc_2F208// ""
0x862e  stind.ref
0x862f  ldarg.s  5
0x8631  ldstr    asc_2F208// ""
0x8636  stind.ref
0x8637  ldarg.1
0x8638  ldstr    aRGrantAsManife// "r:grant/as:ManifestInformation"
0x863d  ldarg.2
0x863e  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x8643  isinst   [System.Xml]System.Xml.XmlElement
0x8648  stloc.0
0x8649  ldloc.0
0x864a  brtrue.s loc_864E
0x864c  ldc.i4.0
0x864d  ret
0x864e  ldloc.0
0x864f  ldstr    aHash// "Hash"
0x8654  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x8659  brtrue.s loc_865D
0x865b  ldc.i4.0
0x865c  ret
0x865d  ldarg.3
0x865e  ldloc.0
0x865f  ldstr    aHash// "Hash"
0x8664  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x8669  stind.ref
0x866a  ldarg.3
0x866b  ldind.ref
0x866c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8671  brfalse.s loc_8675
0x8673  ldc.i4.0
0x8674  ret
0x8675  ldarg.3
0x8676  ldind.ref
0x8677  stloc.1
0x8678  ldc.i4.0
0x8679  stloc.2
0x867a  br.s     loc_8697
0x867c  ldloc.1
0x867d  ldloc.2
0x867e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x8683  stloc.3
0x8684  ldc.i4   0xFF
0x8689  ldloc.3
0x868a  call     unsigned int8 System.Deployment.Internal.CodeSigning.SignedCmiManifest2::HexToByte(char val)
0x868f  bne.un.s loc_8693
0x8691  ldc.i4.0
0x8692  ret
0x8693  ldloc.2
0x8694  ldc.i4.1
0x8695  add
0x8696  stloc.2
0x8697  ldloc.2
0x8698  ldloc.1
0x8699  callvirt instance int32 [mscorlib]System.String::get_Length()
0x869e  blt.s    loc_867C
0x86a0  ldloc.0
0x86a1  ldstr    aDescription// "Description"
0x86a6  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x86ab  brfalse.s loc_86BB
0x86ad  ldarg.s  4
0x86af  ldloc.0
0x86b0  ldstr    aDescription// "Description"
0x86b5  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x86ba  stind.ref
0x86bb  ldloc.0
0x86bc  ldstr    aUrl// "Url"
0x86c1  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x86c6  brfalse.s loc_86D6
0x86c8  ldarg.s  5
0x86ca  ldloc.0
0x86cb  ldstr    aUrl// "Url"
0x86d0  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0x86d5  stind.ref
0x86d6  ldc.i4.1
0x86d7  ret
```
