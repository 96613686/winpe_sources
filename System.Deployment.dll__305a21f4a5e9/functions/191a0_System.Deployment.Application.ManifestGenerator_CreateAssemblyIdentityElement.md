# System.Deployment.Application.ManifestGenerator::CreateAssemblyIdentityElement

- ea: `0x191a0`
- end: `0x19299`
- name: `System.Deployment.Application.ManifestGenerator::CreateAssemblyIdentityElement`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x190c0`
- `0x19180`

## callees

- `0xdb40`
- `0x191a0`

## string_xrefs

- `0x191a6`: `urn:schemas-microsoft-com:asm.v1`
- `0x19231`: `publicKeyToken`
- `0x1923e`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0x191a0  ldarg.0
0x191a1  ldstr    aAssemblyidenti// "assemblyIdentity"
0x191a6  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x191ab  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x191b0  stloc.0
0x191b1  ldarg.1
0x191b2  callvirt instance valuetype System.Deployment.Internal.Isolation.IDENTITY_ATTRIBUTE[] System.Deployment.Application.DefinitionIdentity::get_Attributes()
0x191b7  stloc.1
0x191b8  ldc.i4.3
0x191b9  stloc.2
0x191ba  ldloc.1
0x191bb  stloc.3
0x191bc  ldc.i4.0
0x191bd  stloc.s  4
0x191bf  br       loc_1928D
0x191c4  ldloc.3
0x191c5  ldloc.s  4
0x191c7  ldelem   System.Deployment.Internal.Isolation.IDENTITY_ATTRIBUTE
0x191cc  stloc.s  5
0x191ce  ldloc.s  5
0x191d0  ldfld    string System.Deployment.Internal.Isolation.IDENTITY_ATTRIBUTE::Namespace
0x191d5  stloc.s  6
0x191d7  ldloc.s  5
0x191d9  ldfld    string System.Deployment.Internal.Isolation.IDENTITY_ATTRIBUTE::Name
0x191de  stloc.s  7
0x191e0  ldloc.s  6
0x191e2  brtrue   loc_19275
0x191e7  ldloc.s  7
0x191e9  ldstr    aName// "name"
0x191ee  ldloc.2
0x191ef  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x191f4  brfalse.s loc_191FF
0x191f6  ldstr    aName// "name"
0x191fb  stloc.s  7
0x191fd  br.s     loc_19275
0x191ff  ldloc.s  7
0x19201  ldstr    aVersion_0// "version"
0x19206  ldloc.2
0x19207  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1920c  brfalse.s loc_19217
0x1920e  ldstr    aVersion_0// "version"
0x19213  stloc.s  7
0x19215  br.s     loc_19275
0x19217  ldloc.s  7
0x19219  ldstr    aProcessorarchi// "processorArchitecture"
0x1921e  ldloc.2
0x1921f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x19224  brfalse.s loc_1922F
0x19226  ldstr    aProcessorarchi// "processorArchitecture"
0x1922b  stloc.s  7
0x1922d  br.s     loc_19275
0x1922f  ldloc.s  7
0x19231  ldstr    aPublickeytoken// "publicKeyToken"
0x19236  ldloc.2
0x19237  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1923c  brfalse.s loc_19247
0x1923e  ldstr    aPublickeytoken// "publicKeyToken"
0x19243  stloc.s  7
0x19245  br.s     loc_19275
0x19247  ldloc.s  7
0x19249  ldstr    aType_0// "type"
0x1924e  ldloc.2
0x1924f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x19254  brfalse.s loc_1925F
0x19256  ldstr    aType_0// "type"
0x1925b  stloc.s  7
0x1925d  br.s     loc_19275
0x1925f  ldloc.s  7
0x19261  ldstr    aCulture// "culture"
0x19266  ldloc.2
0x19267  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1926c  brfalse.s loc_19275
0x1926e  ldstr    aLanguage// "language"
0x19273  stloc.s  7
0x19275  ldloc.0
0x19276  ldloc.s  7
0x19278  ldloc.s  6
0x1927a  ldloc.s  5
0x1927c  ldfld    string System.Deployment.Internal.Isolation.IDENTITY_ATTRIBUTE::Value
0x19281  callvirt instance string [System.Xml]System.Xml.XmlElement::SetAttribute(string, string, string)
0x19286  pop
0x19287  ldloc.s  4
0x19289  ldc.i4.1
0x1928a  add
0x1928b  stloc.s  4
0x1928d  ldloc.s  4
0x1928f  ldloc.3
0x19290  ldlen
0x19291  conv.i4
0x19292  blt      loc_191C4
0x19297  ldloc.0
0x19298  ret
```
