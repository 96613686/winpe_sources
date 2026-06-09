# System.Web.Util.UrlPath::MakeRelative

- ea: `0x59a80`
- end: `0x59b74`
- name: `System.Web.Util.UrlPath::MakeRelative`
- size: `244`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x311a0`
- `0x319c0`
- `0x61560`
- `0x770a0`

## callees

- `0x34f20`
- `0x59540`
- `0x59a80`
- `0x59de0`

## string_xrefs

- `0x59a98`: `Path_must_be_rooted`
- `0x59aba`: `Path_must_be_rooted`

## pseudocode

```c

```

## disassembly

```asm
0x59a80  ldarg.0
0x59a81  call     string System.Web.Util.UrlPath::MakeVirtualPathAppAbsolute(string virtualPath)
0x59a86  starg.s  0
0x59a88  ldarg.1
0x59a89  call     string System.Web.Util.UrlPath::MakeVirtualPathAppAbsolute(string virtualPath)
0x59a8e  starg.s  1
0x59a90  ldarg.0
0x59a91  call     bool System.Web.Util.UrlPath::IsRooted(string basepath)
0x59a96  brtrue.s loc_59AB2
0x59a98  ldstr    aPathMustBeRoot// "Path_must_be_rooted"
0x59a9d  ldc.i4.1
0x59a9e  newarr   [mscorlib]System.Object
0x59aa3  dup
0x59aa4  ldc.i4.0
0x59aa5  ldarg.0
0x59aa6  stelem.ref
0x59aa7  call     string System.Web.SR::GetString(string name, object[] args)
0x59aac  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x59ab1  throw
0x59ab2  ldarg.1
0x59ab3  call     bool System.Web.Util.UrlPath::IsRooted(string basepath)
0x59ab8  brtrue.s loc_59AD4
0x59aba  ldstr    aPathMustBeRoot// "Path_must_be_rooted"
0x59abf  ldc.i4.1
0x59ac0  newarr   [mscorlib]System.Object
0x59ac5  dup
0x59ac6  ldc.i4.0
0x59ac7  ldarg.1
0x59ac8  stelem.ref
0x59ac9  call     string System.Web.SR::GetString(string name, object[] args)
0x59ace  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x59ad3  throw
0x59ad4  ldnull
0x59ad5  stloc.0
0x59ad6  ldarg.1
0x59ad7  brfalse.s loc_59AFC
0x59ad9  ldarg.1
0x59ada  ldc.i4.s 0x3F
0x59adc  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x59ae1  stloc.s  4
0x59ae3  ldloc.s  4
0x59ae5  ldc.i4.0
0x59ae6  blt.s    loc_59AFC
0x59ae8  ldarg.1
0x59ae9  ldloc.s  4
0x59aeb  callvirt instance string [mscorlib]System.String::Substring(int32)
0x59af0  stloc.0
0x59af1  ldarg.1
0x59af2  ldc.i4.0
0x59af3  ldloc.s  4
0x59af5  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x59afa  starg.s  1
0x59afc  ldstr    aFileFoo// "file://foo"
0x59b01  ldarg.0
0x59b02  call     string [mscorlib]System.String::Concat(string, string)
0x59b07  newobj   instance void [System]System.Uri::.ctor(string)
0x59b0c  stloc.1
0x59b0d  ldstr    aFileFoo// "file://foo"
0x59b12  ldarg.1
0x59b13  call     string [mscorlib]System.String::Concat(string, string)
0x59b18  newobj   instance void [System]System.Uri::.ctor(string)
0x59b1d  stloc.2
0x59b1e  ldloc.1
0x59b1f  ldloc.2
0x59b20  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x59b25  brfalse.s loc_59B5E
0x59b27  ldarg.1
0x59b28  ldsfld   char[] System.Web.Util.UrlPath::s_slashChars
0x59b2d  callvirt instance int32 [mscorlib]System.String::LastIndexOfAny(char[])
0x59b32  stloc.s  5
0x59b34  ldloc.s  5
0x59b36  ldc.i4.0
0x59b37  blt.s    loc_59B5A
0x59b39  ldloc.s  5
0x59b3b  ldarg.1
0x59b3c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x59b41  ldc.i4.1
0x59b42  sub
0x59b43  bne.un.s loc_59B4D
0x59b45  ldstr    asc_1C6730// "./"
0x59b4a  stloc.3
0x59b4b  br.s     loc_59B66
0x59b4d  ldarg.1
0x59b4e  ldloc.s  5
0x59b50  ldc.i4.1
0x59b51  add
0x59b52  callvirt instance string [mscorlib]System.String::Substring(int32)
0x59b57  stloc.3
0x59b58  br.s     loc_59B66
0x59b5a  ldarg.1
0x59b5b  stloc.3
0x59b5c  br.s     loc_59B66
0x59b5e  ldloc.1
0x59b5f  ldloc.2
0x59b60  callvirt instance string [System]System.Uri::MakeRelative(class [System]System.Uri)
0x59b65  stloc.3
0x59b66  ldloc.3
0x59b67  ldloc.0
0x59b68  ldloc.2
0x59b69  callvirt instance string [System]System.Uri::get_Fragment()
0x59b6e  call     string [mscorlib]System.String::Concat(string, string, string)
0x59b73  ret
```
