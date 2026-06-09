# System.Deployment.Application.UriHelper::UriFromRelativeFilePath

- ea: `0x21950`
- end: `0x219b6`
- name: `System.Deployment.Application.UriHelper::UriFromRelativeFilePath`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x13d30`

## callees

- `0x218d0`
- `0x21950`
- `0x219c0`
- `0x23020`

## string_xrefs

- `0x21958`: `Ex_InvalidRelativePath`

## pseudocode

```c

```

## disassembly

```asm
0x21950  ldarg.1
0x21951  call     bool System.Deployment.Application.UriHelper::IsValidRelativeFilePath(string path)
0x21956  brtrue.s loc_21968
0x21958  ldstr    aExInvalidrelat// "Ex_InvalidRelativePath"
0x2195d  call     string System.Deployment.Application.Resources::GetString(string s)
0x21962  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x21967  throw
0x21968  ldarg.1
0x21969  ldc.i4.s 0x25
0x2196b  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x21970  ldc.i4.0
0x21971  blt.s    loc_21987
0x21973  ldarg.1
0x21974  ldstr    asc_3971A// "%"
0x21979  ldc.i4.s 0x25
0x2197b  call     string [System]System.Uri::HexEscape(char)
0x21980  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x21985  starg.s  1
0x21987  ldarg.1
0x21988  ldc.i4.s 0x23
0x2198a  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x2198f  ldc.i4.0
0x21990  blt.s    loc_219A6
0x21992  ldarg.1
0x21993  ldstr    asc_3971E// "#"
0x21998  ldc.i4.s 0x23
0x2199a  call     string [System]System.Uri::HexEscape(char)
0x2199f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x219a4  starg.s  1
0x219a6  ldarg.0
0x219a7  ldarg.1
0x219a8  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x219ad  stloc.0
0x219ae  ldloc.0
0x219af  call     void System.Deployment.Application.UriHelper::ValidateSupportedScheme(class [System]System.Uri uri)
0x219b4  ldloc.0
0x219b5  ret
```
