# System.IO.Packaging.PackageStore::ValidatePackageUri

- ea: `0x14f60`
- end: `0x14f92`
- name: `System.IO.Packaging.PackageStore::ValidatePackageUri`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14e00`
- `0x14e60`
- `0x14f10`

## callees

- `0x14f60`
- `0x146e40`

## string_xrefs

- `0x14f7c`: `UriMustBeAbsolute`

## pseudocode

```c

```

## disassembly

```asm
0x14f60  ldarg.0
0x14f61  ldnull
0x14f62  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x14f67  brfalse.s loc_14F74
0x14f69  ldstr    aUri// "uri"
0x14f6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14f73  throw
0x14f74  ldarg.0
0x14f75  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x14f7a  brtrue.s loc_14F91
0x14f7c  ldstr    aUrimustbeabsol// "UriMustBeAbsolute"
0x14f81  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x14f86  ldstr    aUri// "uri"
0x14f8b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x14f90  throw
0x14f91  ret
```
