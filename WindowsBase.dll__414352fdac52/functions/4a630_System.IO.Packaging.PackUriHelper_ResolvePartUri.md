# System.IO.Packaging.PackUriHelper::ResolvePartUri

- ea: `0x4a630`
- end: `0x4a6a3`
- name: `System.IO.Packaging.PackUriHelper::ResolvePartUri`
- size: `115`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x21910`
- `0x22170`
- `0x4bca0`
- `0x4c590`
- `0x4ca30`
- `0x4ca80`
- `0x4cad0`
- `0x4cc30`
- `0x4cd20`

## callees

- `0x4a630`
- `0x4a9b0`
- `0x4aa10`
- `0x4acb0`

## string_xrefs

- `0x4a64d`: `targetUri`
- `0x4a639`: `sourcePartUri`

## pseudocode

```c

```

## disassembly

```asm
0x4a630  ldarg.0
0x4a631  ldnull
0x4a632  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a637  brfalse.s loc_4A644
0x4a639  ldstr    aSourceparturi// "sourcePartUri"
0x4a63e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a643  throw
0x4a644  ldarg.1
0x4a645  ldnull
0x4a646  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a64b  brfalse.s loc_4A658
0x4a64d  ldstr    aTargeturi// "targetUri"
0x4a652  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4a657  throw
0x4a658  ldarg.0
0x4a659  call     void System.IO.Packaging.PackUriHelper::ThrowIfAbsoluteUri(class [System]System.Uri uri)
0x4a65e  ldarg.1
0x4a65f  call     void System.IO.Packaging.PackUriHelper::ThrowIfAbsoluteUri(class [System]System.Uri uri)
0x4a664  ldarg.0
0x4a665  call     class [System]System.Uri System.IO.Packaging.PackUriHelper::get_PackageRootUri()
0x4a66a  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4a66f  brfalse.s loc_4A67F
0x4a671  ldsfld   class [System]System.Uri System.IO.Packaging.PackUriHelper::_defaultUri
0x4a676  ldarg.1
0x4a677  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x4a67c  stloc.0
0x4a67d  br.s     loc_4A696
0x4a67f  ldsfld   class [System]System.Uri System.IO.Packaging.PackUriHelper::_defaultUri
0x4a684  ldarg.0
0x4a685  call     class ValidatedPartUri System.IO.Packaging.PackUriHelper::ValidatePartUri(class [System]System.Uri partUri)
0x4a68a  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x4a68f  ldarg.1
0x4a690  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0x4a695  stloc.0
0x4a696  ldloc.0
0x4a697  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x4a69c  ldc.i4.2
0x4a69d  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x4a6a2  ret
```
