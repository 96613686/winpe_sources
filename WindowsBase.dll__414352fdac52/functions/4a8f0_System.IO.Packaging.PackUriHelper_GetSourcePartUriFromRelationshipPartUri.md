# System.IO.Packaging.PackUriHelper::GetSourcePartUriFromRelationshipPartUri

- ea: `0x4a8f0`
- end: `0x4a9a6`
- name: `System.IO.Packaging.PackUriHelper::GetSourcePartUriFromRelationshipPartUri`
- size: `182`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x25110`
- `0x48cd0`
- `0x49780`

## callees

- `0x2c100`
- `0x4a3e0`
- `0x4a7c0`
- `0x4a810`
- `0x4a8f0`
- `0x4a9b0`
- `0x4aa10`
- `0x5a850`
- `0x5a880`

## string_xrefs

- `0x4a8f9`: `relationshipPartUri`
- `0x4a914`: `RelationshipPartUriExpected`

## pseudocode

```c

```

## disassembly

```asm
0x4a8f0  ldarg.0
0x4a8f1  ldnull
0x4a8f2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a8f7  brfalse.s loc_4A904
0x4a8f9  ldstr    aRelationshippa_2// "relationshipPartUri"
0x4a8fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a903  throw
0x4a904  ldarg.0
0x4a905  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x4a90a  starg.s  0
0x4a90c  ldarg.0
0x4a90d  call     bool System.IO.Packaging.PackUriHelper::IsRelationshipPartUri(class [System]System.Uri partUri)
0x4a912  brtrue.s loc_4A924
0x4a914  ldstr    aRelationshippa_3// "RelationshipPartUriExpected"
0x4a919  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4a91e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4a923  throw
0x4a924  call     class [System]System.Uri System.IO.Packaging.PackageRelationship::get_ContainerRelationshipPartName()
0x4a929  ldarg.0
0x4a92a  call     int32 System.IO.Packaging.PackUriHelper::ComparePartUri(class [System]System.Uri firstPartUri, class [System]System.Uri secondPartUri)
0x4a92f  brtrue.s loc_4A937
0x4a931  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::get_PackageRootUri()
0x4a936  ret
0x4a937  ldarg.0
0x4a938  castclass ValidatedPartUri
0x4a93d  callvirt instance string ValidatedPartUri::get_PartUriString()
0x4a942  stloc.0
0x4a943  ldloc.0
0x4a944  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x4a949  stloc.1
0x4a94a  ldloc.0
0x4a94b  ldc.i4.0
0x4a94c  ldloc.0
0x4a94d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a952  ldloc.1
0x4a953  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a958  sub
0x4a959  ldsfld   string System.IO.Packaging.PackUriHelper::_relationshipPartExtensionName
0x4a95e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a963  sub
0x4a964  ldc.i4.1
0x4a965  sub
0x4a966  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4a96b  stloc.0
0x4a96c  ldloc.0
0x4a96d  ldc.i4.0
0x4a96e  ldloc.0
0x4a96f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a974  ldsfld   string System.IO.Packaging.PackUriHelper::_relationshipPartSegmentName
0x4a979  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a97e  sub
0x4a97f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4a984  stloc.0
0x4a985  ldloc.0
0x4a986  ldloc.1
0x4a987  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4a98c  stloc.0
0x4a98d  ldloc.0
0x4a98e  ldsfld   char System.IO.Packaging.PackUriHelper::BackwardSlashChar
0x4a993  ldsfld   char System.IO.Packaging.PackUriHelper::ForwardSlashChar
0x4a998  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x4a99d  stloc.0
0x4a99e  ldloc.0
0x4a99f  ldc.i4.0
0x4a9a0  newobj   instance void ValidatedPartUri::.ctor(string partUriString, bool isRelationshipUri)
0x4a9a5  ret
```
