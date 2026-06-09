# System.Windows.Markup.ReadWriteStreamManager::ReaderSeek

- ea: `0xb1aa0`
- end: `0xb1b1f`
- name: `System.Windows.Markup.ReadWriteStreamManager::ReaderSeek`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0xb1f00`
- `0xb1f30`

## callees

- `0x38c40`
- `0xb1aa0`
- `0xb1c50`
- `0xb1c60`
- `0xb1c70`
- `0xb1ce0`

## string_xrefs

- `0xb1ad1`: `ParserWriterNoSeekEnd`
- `0xb1ae1`: `ParserWriterUnknownOrigin`

## pseudocode

```c

```

## disassembly

```asm
0xb1aa0  ldarg.2
0xb1aa1  switch   loc_B1AB4, loc_B1ABF, loc_B1AD1
0xb1ab2  br.s     loc_B1AE1
0xb1ab4  ldarg.0
0xb1ab5  ldarg.1
0xb1ab6  conv.i4
0xb1ab7  conv.i8
0xb1ab8  call     instance void System.Windows.Markup.ReadWriteStreamManager::set_ReadPosition(int64 value)
0xb1abd  br.s     loc_B1AF1
0xb1abf  ldarg.0
0xb1ac0  ldarg.0
0xb1ac1  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_ReadPosition()
0xb1ac6  ldarg.1
0xb1ac7  add
0xb1ac8  conv.i4
0xb1ac9  conv.i8
0xb1aca  call     instance void System.Windows.Markup.ReadWriteStreamManager::set_ReadPosition(int64 value)
0xb1acf  br.s     loc_B1AF1
0xb1ad1  ldstr    aParserwriterno// "ParserWriterNoSeekEnd"
0xb1ad6  call     string System.Windows.SR::Get(string id)
0xb1adb  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xb1ae0  throw
0xb1ae1  ldstr    aParserwriterun// "ParserWriterUnknownOrigin"
0xb1ae6  call     string System.Windows.SR::Get(string id)
0xb1aeb  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xb1af0  throw
0xb1af1  ldarg.0
0xb1af2  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_ReadPosition()
0xb1af7  ldarg.0
0xb1af8  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_ReaderFirstBufferPosition()
0xb1afd  blt.s    loc_B1B0D
0xb1aff  ldarg.0
0xb1b00  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_ReadPosition()
0xb1b05  ldarg.0
0xb1b06  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_ReadLength()
0xb1b0b  blt.s    loc_B1B18
0xb1b0d  ldstr    aOffset// "offset"
0xb1b12  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb1b17  throw
0xb1b18  ldarg.0
0xb1b19  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_ReadPosition()
0xb1b1e  ret
```
