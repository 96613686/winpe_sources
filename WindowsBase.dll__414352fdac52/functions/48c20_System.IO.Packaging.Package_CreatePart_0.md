# System.IO.Packaging.Package::CreatePart_0

- ea: `0x48c20`
- end: `0x48c9a`
- name: `System.IO.Packaging.Package::CreatePart_0`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x21870`
- `0x48c10`

## callees

- `0x2c100`
- `0x48c20`
- `0x49160`
- `0x49280`
- `0x49300`
- `0x49470`
- `0x49660`
- `0x4aa10`

## string_xrefs

- `0x48c35`: `partUri`
- `0x48c69`: `PartAlreadyExists`

## pseudocode

```c

```

## disassembly

```asm
0x48c20  ldarg.0
0x48c21  call     instance void System.IO.Packaging.Package::ThrowIfObjectDisposed()
0x48c26  ldarg.0
0x48c27  call     instance void System.IO.Packaging.Package::ThrowIfReadOnly()
0x48c2c  ldarg.1
0x48c2d  ldnull
0x48c2e  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x48c33  brfalse.s loc_48C40
0x48c35  ldstr    aParturi// "partUri"
0x48c3a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x48c3f  throw
0x48c40  ldarg.2
0x48c41  brtrue.s loc_48C4E
0x48c43  ldstr    aContenttype// "contentType"
0x48c48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x48c4d  throw
0x48c4e  ldarg.3
0x48c4f  call     void System.IO.Packaging.Package::ThrowIfCompressionOptionInvalid(valuetype System.IO.Packaging.CompressionOption compressionOption)
0x48c54  ldarg.1
0x48c55  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x48c5a  stloc.0
0x48c5b  ldarg.0
0x48c5c  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x48c61  ldloc.0
0x48c62  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::ContainsKey(var<u1>)
0x48c67  brfalse.s loc_48C79
0x48c69  ldstr    aPartalreadyexi// "PartAlreadyExists"
0x48c6e  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x48c73  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x48c78  throw
0x48c79  ldarg.0
0x48c7a  ldloc.0
0x48c7b  ldnull
0x48c7c  call     instance void System.IO.Packaging.Package::AddIfNoPrefixCollisionDetected(class ValidatedPartUri partUri, class System.IO.Packaging.PackagePart part)
0x48c81  ldarg.0
0x48c82  ldloc.0
0x48c83  ldarg.2
0x48c84  ldarg.3
0x48c85  callvirt instance class System.IO.Packaging.PackagePart System.IO.Packaging.Package::CreatePartCore(class [System]System.Uri partUri, string contentType, valuetype System.IO.Packaging.CompressionOption compressionOption)
0x48c8a  stloc.1
0x48c8b  ldarg.0
0x48c8c  ldfld    class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart> System.IO.Packaging.Package::_partList
0x48c91  ldloc.0
0x48c92  ldloc.1
0x48c93  callvirt instance void class [System]System.Collections.Generic.SortedList`2<class ValidatedPartUri, class System.IO.Packaging.PackagePart>::set_Item(var<u1>, !!T0)
0x48c98  ldloc.1
0x48c99  ret
```
