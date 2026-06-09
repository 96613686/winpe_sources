# System.IO.Packaging.PackUriHelper::GetPackageUriComponent

- ea: `0x4ae20`
- end: `0x4ae68`
- name: `System.IO.Packaging.PackUriHelper::GetPackageUriComponent`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4aa60`

## callees

- `0x2c100`
- `0x4ae20`

## string_xrefs

- `0x4ae56`: `InnerPackageUriHasFragment`

## pseudocode

```c

```

## disassembly

```asm
0x4ae20  ldarg.0
0x4ae21  ldc.i4   0x84
0x4ae26  ldc.i4.1
0x4ae27  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x4ae2c  stloc.0
0x4ae2d  ldloc.0
0x4ae2e  ldc.i4.s 0x2C
0x4ae30  ldc.i4.s 0x2F
0x4ae32  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x4ae37  stloc.0
0x4ae38  ldloc.0
0x4ae39  call     string [System]System.Uri::UnescapeDataString(string)
0x4ae3e  newobj   instance void [System]System.Uri::.ctor(string)
0x4ae43  stloc.1
0x4ae44  ldloc.1
0x4ae45  callvirt instance string [System]System.Uri::get_Fragment()
0x4ae4a  ldsfld   string [mscorlib]System.String::Empty
0x4ae4f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x4ae54  brfalse.s loc_4AE66
0x4ae56  ldstr    aInnerpackageur// "InnerPackageUriHasFragment"
0x4ae5b  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ae60  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ae65  throw
0x4ae66  ldloc.1
0x4ae67  ret
```
