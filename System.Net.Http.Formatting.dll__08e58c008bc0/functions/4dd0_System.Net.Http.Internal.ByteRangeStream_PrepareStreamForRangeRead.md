# System.Net.Http.Internal.ByteRangeStream::PrepareStreamForRangeRead

- ea: `0x4dd0`
- end: `0x4e36`
- name: `System.Net.Http.Internal.ByteRangeStream::PrepareStreamForRangeRead`
- size: `102`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x4c30`
- `0x4c50`
- `0x4c60`
- `0x4c80`

## callees

- `0x4dd0`
- `0x5270`

## pseudocode

```c

```

## disassembly

```asm
0x4dd0  ldarg.1
0x4dd1  ldc.i4.0
0x4dd2  bgt.s    loc_4DD6
0x4dd4  ldarg.1
0x4dd5  ret
0x4dd6  ldarg.0
0x4dd7  ldfld    int64 System.Net.Http.Internal.ByteRangeStream::_currentCount
0x4ddc  ldarg.0
0x4ddd  ldfld    int64 System.Net.Http.Internal.ByteRangeStream::_totalCount
0x4de2  blt.s    loc_4DE6
0x4de4  ldc.i4.0
0x4de5  ret
0x4de6  ldarg.1
0x4de7  conv.i8
0x4de8  ldarg.0
0x4de9  ldfld    int64 System.Net.Http.Internal.ByteRangeStream::_totalCount
0x4dee  ldarg.0
0x4def  ldfld    int64 System.Net.Http.Internal.ByteRangeStream::_currentCount
0x4df4  sub
0x4df5  call     int64 [mscorlib]System.Math::Min(int64, int64)
0x4dfa  stloc.0
0x4dfb  ldarg.0
0x4dfc  ldfld    int64 System.Net.Http.Internal.ByteRangeStream::_lowerbounds
0x4e01  ldarg.0
0x4e02  ldfld    int64 System.Net.Http.Internal.ByteRangeStream::_currentCount
0x4e07  add
0x4e08  stloc.1
0x4e09  ldarg.0
0x4e0a  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0x4e0f  callvirt instance int64 [mscorlib]System.IO.Stream::get_Position()
0x4e14  stloc.2
0x4e15  ldloc.1
0x4e16  ldloc.2
0x4e17  beq.s    loc_4E25
0x4e19  ldarg.0
0x4e1a  call     instance class [mscorlib]System.IO.Stream System.Net.Http.Internal.DelegatingStream::get_InnerStream()
0x4e1f  ldloc.1
0x4e20  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x4e25  ldarg.0
0x4e26  ldarg.0
0x4e27  ldfld    int64 System.Net.Http.Internal.ByteRangeStream::_currentCount
0x4e2c  ldloc.0
0x4e2d  add
0x4e2e  stfld    int64 System.Net.Http.Internal.ByteRangeStream::_currentCount
0x4e33  ldloc.0
0x4e34  conv.i4
0x4e35  ret
```
