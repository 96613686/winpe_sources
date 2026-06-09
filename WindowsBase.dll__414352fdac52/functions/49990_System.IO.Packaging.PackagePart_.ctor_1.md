# System.IO.Packaging.PackagePart::.ctor_1

- ea: `0x49990`
- end: `0x49a0d`
- name: `System.IO.Packaging.PackagePart::.ctor_1`
- size: `125`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x49970`
- `0x49980`
- `0x4b700`
- `0x4b720`
- `0x4b740`

## callees

- `0xf780`
- `0x49300`
- `0x49990`
- `0x4a810`
- `0x4aa10`

## string_xrefs

- `0x499b4`: `partUri`

## pseudocode

```c

```

## disassembly

```asm
0x49990  ldarg.0
0x49991  ldc.i4.m1
0x49992  stfld    valuetype System.IO.Packaging.CompressionOption System.IO.Packaging.PackagePart::_compressionOption
0x49997  ldarg.0
0x49998  call     instance void [mscorlib]System.Object::.ctor()
0x4999d  ldarg.1
0x4999e  brtrue.s loc_499AB
0x499a0  ldstr    aPackage// "package"
0x499a5  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x499aa  throw
0x499ab  ldarg.2
0x499ac  ldnull
0x499ad  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x499b2  brfalse.s loc_499BF
0x499b4  ldstr    aParturi// "partUri"
0x499b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x499be  throw
0x499bf  ldarg.s  4
0x499c1  call     void System.IO.Packaging.Package::ThrowIfCompressionOptionInvalid(valuetype System.IO.Packaging.CompressionOption compressionOption)
0x499c6  ldarg.0
0x499c7  ldarg.2
0x499c8  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x499cd  stfld    class ValidatedPartUri System.IO.Packaging.PackagePart::_uri
0x499d2  ldarg.0
0x499d3  ldarg.1
0x499d4  stfld    class System.IO.Packaging.Package System.IO.Packaging.PackagePart::_container
0x499d9  ldarg.3
0x499da  brtrue.s loc_499E5
0x499dc  ldarg.0
0x499dd  ldnull
0x499de  stfld    class MS.Internal.ContentType System.IO.Packaging.PackagePart::_contentType
0x499e3  br.s     loc_499F1
0x499e5  ldarg.0
0x499e6  ldarg.3
0x499e7  newobj   instance void MS.Internal.ContentType::.ctor(string contentType)
0x499ec  stfld    class MS.Internal.ContentType System.IO.Packaging.PackagePart::_contentType
0x499f1  ldarg.0
0x499f2  ldnull
0x499f3  stfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IO.Stream> System.IO.Packaging.PackagePart::_requestedStreams
0x499f8  ldarg.0
0x499f9  ldarg.s  4
0x499fb  stfld    valuetype System.IO.Packaging.CompressionOption System.IO.Packaging.PackagePart::_compressionOption
0x49a00  ldarg.0
0x49a01  ldarg.2
0x49a02  call     bool System.IO.Packaging.PackUriHelper::IsRelationshipPartUri(class [System]System.Uri partUri)
0x49a07  stfld    bool System.IO.Packaging.PackagePart::_isRelationshipPart
0x49a0c  ret
```
