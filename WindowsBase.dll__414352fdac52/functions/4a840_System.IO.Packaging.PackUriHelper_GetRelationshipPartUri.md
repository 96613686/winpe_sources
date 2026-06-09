# System.IO.Packaging.PackUriHelper::GetRelationshipPartUri

- ea: `0x4a840`
- end: `0x4a8ef`
- name: `System.IO.Packaging.PackUriHelper::GetRelationshipPartUri`
- size: `175`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x212a0`
- `0x252b0`
- `0x48cd0`

## callees

- `0x2c100`
- `0x4a3e0`
- `0x4a810`
- `0x4a840`
- `0x4a9b0`
- `0x4aa10`
- `0x5a850`
- `0x5a880`

## string_xrefs

- `0x4a849`: `partUri`
- `0x4a87e`: `RelationshipPartUriNotExpected`

## pseudocode

```c

```

## disassembly

```asm
0x4a840  ldarg.0
0x4a841  ldnull
0x4a842  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a847  brfalse.s loc_4A854
0x4a849  ldstr    aParturi// "partUri"
0x4a84e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a853  throw
0x4a854  ldarg.0
0x4a855  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::get_PackageRootUri()
0x4a85a  ldc.i4   0x80000000
0x4a85f  ldc.i4.1
0x4a860  ldc.i4.4
0x4a861  call     int32 [System]System.Uri::Compare(class [System]System.Uri, class [System]System.Uri, valuetype [System]System.UriComponents, valuetype [System]System.UriFormat, valuetype [mscorlib]System.StringComparison)
0x4a866  brtrue.s loc_4A86E
0x4a868  call     class [System]System.Uri System.IO.Packaging.PackageRelationship::get_ContainerRelationshipPartName()
0x4a86d  ret
0x4a86e  ldarg.0
0x4a86f  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x4a874  starg.s  0
0x4a876  ldarg.0
0x4a877  call     bool System.IO.Packaging.PackUriHelper::IsRelationshipPartUri(class [System]System.Uri partUri)
0x4a87c  brfalse.s loc_4A88E
0x4a87e  ldstr    aRelationshippa_1// "RelationshipPartUriNotExpected"
0x4a883  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4a888  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4a88d  throw
0x4a88e  ldarg.0
0x4a88f  castclass ValidatedPartUri
0x4a894  callvirt instance string ValidatedPartUri::get_PartUriString()
0x4a899  stloc.0
0x4a89a  ldloc.0
0x4a89b  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x4a8a0  stloc.1
0x4a8a1  ldloc.0
0x4a8a2  ldc.i4.0
0x4a8a3  ldloc.0
0x4a8a4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a8a9  ldloc.1
0x4a8aa  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a8af  sub
0x4a8b0  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4a8b5  stloc.0
0x4a8b6  ldloc.0
0x4a8b7  ldsfld   string System.IO.Packaging.PackUriHelper::_relationshipPartSegmentName
0x4a8bc  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4a8c1  stloc.0
0x4a8c2  ldloc.0
0x4a8c3  ldloc.1
0x4a8c4  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4a8c9  stloc.0
0x4a8ca  ldloc.0
0x4a8cb  ldsfld   string System.IO.Packaging.PackUriHelper::_relationshipPartExtensionName
0x4a8d0  call     string [mscorlib]System.String::Concat(string, string)
0x4a8d5  stloc.0
0x4a8d6  ldloc.0
0x4a8d7  ldsfld   char System.IO.Packaging.PackUriHelper::BackwardSlashChar
0x4a8dc  ldsfld   char System.IO.Packaging.PackUriHelper::ForwardSlashChar
0x4a8e1  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x4a8e6  stloc.0
0x4a8e7  ldloc.0
0x4a8e8  ldc.i4.1
0x4a8e9  newobj   instance void ValidatedPartUri::.ctor(string partUriString, bool isRelationshipUri)
0x4a8ee  ret
```
