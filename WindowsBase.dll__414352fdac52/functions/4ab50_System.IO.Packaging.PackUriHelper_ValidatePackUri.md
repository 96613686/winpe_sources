# System.IO.Packaging.PackUriHelper::ValidatePackUri

- ea: `0x4ab50`
- end: `0x4aba0`
- name: `System.IO.Packaging.PackUriHelper::ValidatePackUri`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4aa60`

## callees

- `0x2c100`
- `0x4ab50`

## string_xrefs

- `0x4ab6c`: `UriShouldBeAbsolute`
- `0x4ab59`: `packUri`
- `0x4ab8e`: `UriShouldBePackScheme`

## pseudocode

```c

```

## disassembly

```asm
0x4ab50  ldarg.0
0x4ab51  ldnull
0x4ab52  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4ab57  brfalse.s loc_4AB64
0x4ab59  ldstr    aPackuri// "packUri"
0x4ab5e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4ab63  throw
0x4ab64  ldarg.0
0x4ab65  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x4ab6a  brtrue.s loc_4AB7C
0x4ab6c  ldstr    aUrishouldbeabs// "UriShouldBeAbsolute"
0x4ab71  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ab76  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ab7b  throw
0x4ab7c  ldarg.0
0x4ab7d  callvirt instance string [System]System.Uri::get_Scheme()
0x4ab82  ldsfld   string System.IO.Packaging.PackUriHelper::UriSchemePack
0x4ab87  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x4ab8c  brfalse.s loc_4AB9E
0x4ab8e  ldstr    aUrishouldbepac// "UriShouldBePackScheme"
0x4ab93  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ab98  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ab9d  throw
0x4ab9e  ldarg.0
0x4ab9f  ret
```
