# Util.StringUtilities::GetStringSize

- ea: `0x13c0`
- end: `0x13e0`
- name: `Util.StringUtilities::GetStringSize`
- size: `32`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1930`
- `0x19c0`
- `0x21d0`
- `0x22a0`

## callees

- `0x150`

## pseudocode

```c

```

## disassembly

```asm
0x13c0  ldarga.s 0
0x13c2  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x13c7  ldc.i4   0x100
0x13cc  conv.i8
0x13cd  ldarg.1
0x13ce  call     modopt([mscorlib]System.Runtime.CompilerServices.CallConvCdecl) modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 StringCchLengthW(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) unsigned int16* psz, unsigned int64 cchMax, unsigned int64* pcchLength)
0x13d3  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x13d8  ldarg.1
0x13d9  dup
0x13da  ldind.i8
0x13db  ldc.i4.1
0x13dc  conv.i8
0x13dd  add
0x13de  stind.i8
0x13df  ret
```
