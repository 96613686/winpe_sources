# System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::ReadFormUrlEncoded

- ea: `0x7690`
- end: `0x770f`
- name: `System.Net.Http.Formatting.FormUrlEncodedMediaTypeFormatter::ReadFormUrlEncoded`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x7620`

## callees

- `0x3370`
- `0x33b0`
- `0x7690`
- `0x9740`
- `0x9790`
- `0xb4b0`
- `0xb4c0`

## pseudocode

```c

```

## disassembly

```asm
0x7690  ldarg.1
0x7691  newarr   [mscorlib]System.Byte
0x7696  stloc.0
0x7697  ldc.i4.0
0x7698  stloc.2
0x7699  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::.ctor()
0x769e  stloc.3
0x769f  ldloc.3
0x76a0  ldc.i8   0x7FFFFFFFFFFFFFFF
0x76a9  newobj   instance void System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::.ctor(class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> nameValuePairs, int64 maxMessageSize)
0x76ae  stloc.s  4
0x76b0  nop
0x76b1  ldarg.0
0x76b2  ldloc.0
0x76b3  ldc.i4.0
0x76b4  ldloc.0
0x76b5  ldlen
0x76b6  conv.i4
0x76b7  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x76bc  stloc.1
0x76bd  ldloc.1
0x76be  brtrue.s loc_76C2
0x76c0  ldc.i4.1
0x76c1  stloc.2
0x76c2  leave.s  loc_76D5
0x76c4  call     string System.Net.Http.Properties.Resources::get_ErrorReadingFormUrlEncodedStream()
0x76c9  ldc.i4.0
0x76ca  newarr   [mscorlib]System.Object
0x76cf  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(class [mscorlib]System.Exception innerException, string messageFormat, object[] messageArgs)
0x76d4  throw
0x76d5  ldc.i4.0
0x76d6  stloc.s  6
0x76d8  ldloc.s  4
0x76da  ldloc.0
0x76db  ldloc.1
0x76dc  ldloca.s 6
0x76de  ldloc.2
0x76df  callvirt instance valuetype System.Net.Http.Formatting.Parsers.ParserState System.Net.Http.Formatting.Parsers.FormUrlEncodedParser::ParseBuffer(unsigned int8[] buffer, int32 bytesReady, int32& bytesConsumed, bool isFinal)
0x76e4  stloc.s  5
0x76e6  ldloc.s  5
0x76e8  brfalse.s loc_770A
0x76ea  ldloc.s  5
0x76ec  ldc.i4.1
0x76ed  beq.s    loc_770A
0x76ef  call     string System.Net.Http.Properties.Resources::get_FormUrlEncodedParseError()
0x76f4  ldc.i4.1
0x76f5  newarr   [mscorlib]System.Object
0x76fa  dup
0x76fb  ldc.i4.0
0x76fc  ldloc.s  6
0x76fe  box      [mscorlib]System.Int32
0x7703  stelem.ref
0x7704  call     class [mscorlib]System.InvalidOperationException System.Web.Http.Error::InvalidOperation(string messageFormat, object[] messageArgs)
0x7709  throw
0x770a  ldloc.2
0x770b  brfalse.s loc_76B0
0x770d  ldloc.3
0x770e  ret
```
