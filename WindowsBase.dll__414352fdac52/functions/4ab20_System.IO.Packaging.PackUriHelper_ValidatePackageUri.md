# System.IO.Packaging.PackUriHelper::ValidatePackageUri

- ea: `0x4ab20`
- end: `0x4ab4e`
- name: `System.IO.Packaging.PackUriHelper::ValidatePackageUri`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4a4d0`

## callees

- `0x2c100`
- `0x4ab20`

## string_xrefs

- `0x4ab29`: `packageUri`
- `0x4ab3c`: `UriShouldBeAbsolute`

## pseudocode

```c

```

## disassembly

```asm
0x4ab20  ldarg.0
0x4ab21  ldnull
0x4ab22  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x4ab27  brfalse.s loc_4AB34
0x4ab29  ldstr    aPackageuri// "packageUri"
0x4ab2e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4ab33  throw
0x4ab34  ldarg.0
0x4ab35  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x4ab3a  brtrue.s loc_4AB4C
0x4ab3c  ldstr    aUrishouldbeabs// "UriShouldBeAbsolute"
0x4ab41  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ab46  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ab4b  throw
0x4ab4c  ldarg.0
0x4ab4d  ret
```
