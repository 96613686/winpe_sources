# System.Windows.Media.FontFamily::.ctor_0

- ea: `0x80b10`
- end: `0x80b58`
- name: `System.Windows.Media.FontFamily::.ctor_0`
- size: `72`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x80b00`
- `0x81090`
- `0x1157a0`
- `0x12b870`
- `0x12b950`

## callees

- `0x80b10`
- `0x129f90`
- `0x146e40`

## string_xrefs

- `0x80b35`: `UriNotAbsolute`
- `0x80b3f`: `baseUri`

## pseudocode

```c

```

## disassembly

```asm
0x80b10  ldarg.0
0x80b11  call     instance void [mscorlib]System.Object::.ctor()
0x80b16  ldarg.2
0x80b17  brtrue.s loc_80B24
0x80b19  ldstr    aFamilyname// "familyName"
0x80b1e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x80b23  throw
0x80b24  ldarg.1
0x80b25  ldnull
0x80b26  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x80b2b  brfalse.s loc_80B4A
0x80b2d  ldarg.1
0x80b2e  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x80b33  brtrue.s loc_80B4A
0x80b35  ldstr    aUrinotabsolute// "UriNotAbsolute"
0x80b3a  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x80b3f  ldstr    aBaseuri_0// "baseUri"
0x80b44  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x80b49  throw
0x80b4a  ldarg.0
0x80b4b  ldarg.2
0x80b4c  ldarg.1
0x80b4d  newobj   instance void MS.Internal.FontFace.FontFamilyIdentifier::.ctor(string friendlyName, class [System]System.Uri baseUri)
0x80b52  stfld    valuetype MS.Internal.FontFace.FontFamilyIdentifier System.Windows.Media.FontFamily::_familyIdentifier
0x80b57  ret
```
