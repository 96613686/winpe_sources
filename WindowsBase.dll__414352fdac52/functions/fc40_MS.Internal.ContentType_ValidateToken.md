# MS.Internal.ContentType::ValidateToken

- ea: `0xfc40`
- end: `0xfc9c`
- name: `MS.Internal.ContentType::ValidateToken`
- size: `92`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0xfa80`
- `0xfad0`
- `0xfca0`

## callees

- `0xfc40`
- `0xfd90`
- `0xfdb0`
- `0x2c100`

## string_xrefs

- `0xfc4d`: `InvalidToken`
- `0xfc7d`: `InvalidToken`

## pseudocode

```c

```

## disassembly

```asm
0xfc40  ldarg.0
0xfc41  ldsfld   string [mscorlib]System.String::Empty
0xfc46  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xfc4b  brtrue.s loc_FC5D
0xfc4d  ldstr    aInvalidtoken// "InvalidToken"
0xfc52  call     string MS.Internal.WindowsBase.SR::Get(string id)
0xfc57  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfc5c  throw
0xfc5d  ldc.i4.0
0xfc5e  stloc.0
0xfc5f  br.s     loc_FC91
0xfc61  ldarg.0
0xfc62  ldloc.0
0xfc63  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xfc68  call     bool MS.Internal.ContentType::IsAsciiLetterOrDigit(char character)
0xfc6d  brtrue.s loc_FC8D
0xfc6f  ldarg.0
0xfc70  ldloc.0
0xfc71  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0xfc76  call     bool MS.Internal.ContentType::IsAllowedCharacter(char character)
0xfc7b  brtrue.s loc_FC8D
0xfc7d  ldstr    aInvalidtoken// "InvalidToken"
0xfc82  call     string MS.Internal.WindowsBase.SR::Get(string id)
0xfc87  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfc8c  throw
0xfc8d  ldloc.0
0xfc8e  ldc.i4.1
0xfc8f  add
0xfc90  stloc.0
0xfc91  ldloc.0
0xfc92  ldarg.0
0xfc93  callvirt instance int32 [mscorlib]System.String::get_Length()
0xfc98  blt.s    loc_FC61
0xfc9a  ldarg.0
0xfc9b  ret
```
