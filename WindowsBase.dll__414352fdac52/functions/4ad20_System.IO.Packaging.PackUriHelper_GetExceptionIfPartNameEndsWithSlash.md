# System.IO.Packaging.PackUriHelper::GetExceptionIfPartNameEndsWithSlash

- ea: `0x4ad20`
- end: `0x4ad4d`
- name: `System.IO.Packaging.PackUriHelper::GetExceptionIfPartNameEndsWithSlash`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4abe0`
- `0x4ad10`

## callees

- `0x2c100`
- `0x4ad20`

## string_xrefs

- `0x4ad3b`: `PartUriShouldNotEndWithForwardSlash`

## pseudocode

```c

```

## disassembly

```asm
0x4ad20  ldarg.0
0x4ad21  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4ad26  ldc.i4.0
0x4ad27  ble.s    loc_4AD4B
0x4ad29  ldarg.0
0x4ad2a  ldarg.0
0x4ad2b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4ad30  ldc.i4.1
0x4ad31  sub
0x4ad32  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4ad37  ldc.i4.s 0x2F
0x4ad39  bne.un.s loc_4AD4B
0x4ad3b  ldstr    aParturishouldn// "PartUriShouldNotEndWithForwardSlash"
0x4ad40  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ad45  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ad4a  ret
0x4ad4b  ldnull
0x4ad4c  ret
```
