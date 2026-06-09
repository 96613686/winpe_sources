# System.Windows.Media.Fonts::GetFontFamilies_1

- ea: `0x813a0`
- end: `0x8146e`
- name: `System.Windows.Media.Fonts::GetFontFamilies_1`
- size: `206`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x81360`
- `0x81380`
- `0x81470`
- `0x81490`
- `0x814c0`

## callees

- `0x813a0`
- `0x81500`
- `0x12c7d0`
- `0x12c890`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x813b1`: `UriNotAbsolute`
- `0x813bb`: `baseUri`
- `0x8140c`: `baseUri`
- `0x8141e`: `baseUri`
- `0x813e1`: `InvalidAbsoluteUriInFontFamilyName`
- `0x81411`: `NullBaseUriParam`

## pseudocode

```c

```

## disassembly

```asm
0x813a0  ldarg.0
0x813a1  ldnull
0x813a2  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x813a7  brfalse.s loc_813C6
0x813a9  ldarg.0
0x813aa  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x813af  brtrue.s loc_813C6
0x813b1  ldstr    aUrinotabsolute// "UriNotAbsolute"
0x813b6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x813bb  ldstr    aBaseuri_0// "baseUri"
0x813c0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x813c5  throw
0x813c6  ldarg.1
0x813c7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x813cc  brtrue.s loc_81403
0x813ce  ldarg.1
0x813cf  ldc.i4.1
0x813d0  ldloca.s 0
0x813d2  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x813d7  brfalse.s loc_81403
0x813d9  ldloc.0
0x813da  call     bool MS.Internal.FontCache.Util::IsSupportedSchemeForAbsoluteFontFamilyUri(class [System]System.Uri absoluteUri)
0x813df  brtrue.s loc_813F6
0x813e1  ldstr    aInvalidabsolut// "InvalidAbsoluteUriInFontFamilyName"
0x813e6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x813eb  ldstr    aLocation_0// "location"
0x813f0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x813f5  throw
0x813f6  ldloc.0
0x813f7  ldc.i4.s 0x7F
0x813f9  ldc.i4.3
0x813fa  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x813ff  starg.s  1
0x81401  br.s     loc_81465
0x81403  ldarg.0
0x81404  ldnull
0x81405  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x8140a  brfalse.s loc_81437
0x8140c  ldstr    aBaseuri_0// "baseUri"
0x81411  ldstr    aNullbaseuripar// "NullBaseUriParam"
0x81416  ldc.i4.2
0x81417  newarr   [mscorlib]System.Object
0x8141c  dup
0x8141d  ldc.i4.0
0x8141e  ldstr    aBaseuri_0// "baseUri"
0x81423  stelem.ref
0x81424  dup
0x81425  ldc.i4.1
0x81426  ldstr    aLocation_0// "location"
0x8142b  stelem.ref
0x8142c  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x81431  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x81436  throw
0x81437  ldarg.1
0x81438  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8143d  brfalse.s loc_81448
0x8143f  ldstr    asc_16775E// "./"
0x81444  starg.s  1
0x81446  br.s     loc_8145D
0x81448  ldarg.1
0x81449  call     bool MS.Internal.FontCache.Util::IsReferenceToWindowsFonts(string s)
0x8144e  brfalse.s loc_8145D
0x81450  ldstr    asc_16775E// "./"
0x81455  ldarg.1
0x81456  call     string [mscorlib]System.String::Concat(string, string)
0x8145b  starg.s  1
0x8145d  ldarg.0
0x8145e  ldarg.1
0x8145f  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x81464  stloc.0
0x81465  ldloc.0
0x81466  ldarg.0
0x81467  ldarg.1
0x81468  call     class [mscorlib]System.Collections.Generic.ICollection`1<class System.Windows.Media.FontFamily> System.Windows.Media.Fonts::CreateFamilyCollection(class [System]System.Uri fontLocation, class [System]System.Uri fontFamilyBaseUri, string fontFamilyLocationReference)
0x8146d  ret
```
