# System.IO.Packaging.PackUriHelper::GetExceptionIfPartNameStartsWithTwoSlashes

- ea: `0x4ad60`
- end: `0x4ad91`
- name: `System.IO.Packaging.PackUriHelper::GetExceptionIfPartNameStartsWithTwoSlashes`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4abe0`
- `0x4ad50`

## callees

- `0x2c100`
- `0x4ad60`

## string_xrefs

- `0x4ad7f`: `PartUriShouldNotStartWithTwoForwardSlashes`

## pseudocode

```c

```

## disassembly

```asm
0x4ad60  ldarg.0
0x4ad61  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4ad66  ldc.i4.1
0x4ad67  ble.s    loc_4AD8F
0x4ad69  ldarg.0
0x4ad6a  ldc.i4.0
0x4ad6b  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4ad70  ldc.i4.s 0x2F
0x4ad72  bne.un.s loc_4AD8F
0x4ad74  ldarg.0
0x4ad75  ldc.i4.1
0x4ad76  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4ad7b  ldc.i4.s 0x2F
0x4ad7d  bne.un.s loc_4AD8F
0x4ad7f  ldstr    aParturishouldn_0// "PartUriShouldNotStartWithTwoForwardSlas"...
0x4ad84  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x4ad89  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ad8e  ret
0x4ad8f  ldnull
0x4ad90  ret
```
