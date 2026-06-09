# System.Windows.Markup.ReadWriteStreamManager::WriterSeek

- ea: `0xb1900`
- end: `0xb197f`
- name: `System.Windows.Markup.ReadWriteStreamManager::WriterSeek`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0xb1e20`

## callees

- `0x38c40`
- `0xb1900`
- `0xb1c70`
- `0xb1c90`
- `0xb1ca0`
- `0xb1cb0`

## string_xrefs

- `0xb1931`: `ParserWriterNoSeekEnd`
- `0xb1941`: `ParserWriterUnknownOrigin`

## pseudocode

```c

```

## disassembly

```asm
0xb1900  ldarg.2
0xb1901  switch   loc_B1914, loc_B191F, loc_B1931
0xb1912  br.s     loc_B1941
0xb1914  ldarg.0
0xb1915  ldarg.1
0xb1916  conv.i4
0xb1917  conv.i8
0xb1918  call     instance void System.Windows.Markup.ReadWriteStreamManager::set_WritePosition(int64 value)
0xb191d  br.s     loc_B1951
0xb191f  ldarg.0
0xb1920  ldarg.0
0xb1921  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_WritePosition()
0xb1926  ldarg.1
0xb1927  add
0xb1928  conv.i4
0xb1929  conv.i8
0xb192a  call     instance void System.Windows.Markup.ReadWriteStreamManager::set_WritePosition(int64 value)
0xb192f  br.s     loc_B1951
0xb1931  ldstr    aParserwriterno// "ParserWriterNoSeekEnd"
0xb1936  call     string System.Windows.SR::Get(string id)
0xb193b  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xb1940  throw
0xb1941  ldstr    aParserwriterun// "ParserWriterUnknownOrigin"
0xb1946  call     string System.Windows.SR::Get(string id)
0xb194b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xb1950  throw
0xb1951  ldarg.0
0xb1952  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_WritePosition()
0xb1957  ldarg.0
0xb1958  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_WriteLength()
0xb195d  bgt.s    loc_B196D
0xb195f  ldarg.0
0xb1960  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_WritePosition()
0xb1965  ldarg.0
0xb1966  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_ReadLength()
0xb196b  bge.s    loc_B1978
0xb196d  ldstr    aOffset// "offset"
0xb1972  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xb1977  throw
0xb1978  ldarg.0
0xb1979  call     instance int64 System.Windows.Markup.ReadWriteStreamManager::get_WritePosition()
0xb197e  ret
```
