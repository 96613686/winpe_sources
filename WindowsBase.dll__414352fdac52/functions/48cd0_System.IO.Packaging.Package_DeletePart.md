# System.IO.Packaging.Package::DeletePart

- ea: `0x48cd0`
- end: `0x48db6`
- name: `System.IO.Packaging.Package::DeletePart`
- size: `230`
- prototype: ``
- caller_count: `6`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x21120`
- `0x48cd0`
- `0x4c590`
- `0x4c980`
- `0x4ca30`
- `0x4cb20`

## callees

- `0x48ca0`
- `0x48cc0`
- `0x48cd0`
- `0x49180`
- `0x49220`
- `0x49280`
- `0x49660`
- `0x496a0`
- `0x49a10`
- `0x49c60`
- `0x49c90`
- `0x49d00`
- `0x4a810`
- `0x4a840`
- `0x4a8f0`
- `0x4a9b0`
- `0x4aa10`

## string_xrefs

- `0x48cf0`: `partUri`
- `0x48cdd`: `DeletePart`

## pseudocode

```c

```

## disassembly

```asm
0x48cd0  ldarg.0
0x48cd1  call     instance void System.IO.Packaging.Package::ThrowIfObjectDisposed()
0x48cd6  ldarg.0
0x48cd7  call     instance void System.IO.Packaging.Package::ThrowIfReadOnly()
0x48cdc  ldarg.0
0x48cdd  ldstr    aDeletepart// "DeletePart"
0x48ce2  call     instance void System.IO.Packaging.Package::ThrowIfInStreamingCreation(string methodName)
0x48ce7  ldarg.1
0x48ce8  ldnull
0x48ce9  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x48cee  brfalse.s loc_48CFB
0x48cf0  ldstr    aParturi// "partUri"
0x48cf5  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x48cfa  throw
0x48cfb  ldarg.1
0x48cfc  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x48d01  stloc.0
0x48d02  ldarg.0
0x48d03  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x48d08  ldloc.0
0x48d09  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::ContainsKey(var<u1>)
0x48d0e  brfalse.s loc_48D60
0x48d10  ldarg.0
0x48d11  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x48d16  ldloc.0
0x48d17  callvirt instance var<u1> class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::get_Item(void)
0x48d1c  callvirt instance class [System]System.Uri System.IO.Packaging.PackagePart::get_Uri()
0x48d21  castclass ValidatedPartUri
0x48d26  stloc.0
0x48d27  ldarg.0
0x48d28  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x48d2d  ldloc.0
0x48d2e  callvirt instance var<u1> class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::get_Item(void)
0x48d33  ldc.i4.1
0x48d34  callvirt instance void System.IO.Packaging.PackagePart::set_IsDeleted(bool value)
0x48d39  ldarg.0
0x48d3a  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x48d3f  ldloc.0
0x48d40  callvirt instance var<u1> class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::get_Item(void)
0x48d45  callvirt instance void System.IO.Packaging.PackagePart::Close()
0x48d4a  ldarg.0
0x48d4b  ldloc.0
0x48d4c  callvirt instance void System.IO.Packaging.Package::DeletePartCore(class [System]System.Uri partUri)
0x48d51  ldarg.0
0x48d52  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x48d57  ldloc.0
0x48d58  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::Remove(var<u1>)
0x48d5d  pop
0x48d5e  br.s     loc_48D67
0x48d60  ldarg.0
0x48d61  ldloc.0
0x48d62  callvirt instance void System.IO.Packaging.Package::DeletePartCore(class [System]System.Uri partUri)
0x48d67  ldloc.0
0x48d68  call     bool System.IO.Packaging.PackUriHelper::IsRelationshipPartUri(class [System]System.Uri partUri)
0x48d6d  brfalse.s loc_48DA9
0x48d6f  ldloc.0
0x48d70  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::GetSourcePartUriFromRelationshipPartUri(class [System]System.Uri relationshipPartUri)
0x48d75  stloc.1
0x48d76  ldloc.1
0x48d77  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::get_PackageRootUri()
0x48d7c  ldc.i4   0x80000000
0x48d81  ldc.i4.1
0x48d82  ldc.i4.4
0x48d83  call     int32 [System]System.Uri::Compare(class [System]System.Uri, class [System]System.Uri, valuetype [System]System.UriComponents, valuetype [System]System.UriFormat, valuetype [mscorlib]System.StringComparison)
0x48d88  brtrue.s loc_48D91
0x48d8a  ldarg.0
0x48d8b  call     instance void System.IO.Packaging.Package::ClearRelationships()
0x48d90  ret
0x48d91  ldarg.0
0x48d92  ldloc.1
0x48d93  callvirt instance bool System.IO.Packaging.Package::PartExists(class [System]System.Uri partUri)
0x48d98  brfalse.s loc_48DB5
0x48d9a  ldarg.0
0x48d9b  ldloc.1
0x48d9c  call     instance class System.IO.Packaging.PackagePart System.IO.Packaging.Package::GetPart(class [System]System.Uri partUri)
0x48da1  stloc.2
0x48da2  ldloc.2
0x48da3  callvirt instance void System.IO.Packaging.PackagePart::ClearRelationships()
0x48da8  ret
0x48da9  ldarg.0
0x48daa  ldloc.0
0x48dab  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::GetRelationshipPartUri(class [System]System.Uri partUri)
0x48db0  call     instance void System.IO.Packaging.Package::DeletePart(class [System]System.Uri partUri)
0x48db5  ret
```
