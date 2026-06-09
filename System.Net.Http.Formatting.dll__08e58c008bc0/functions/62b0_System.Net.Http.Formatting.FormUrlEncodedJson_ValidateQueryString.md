# System.Net.Http.Formatting.FormUrlEncodedJson::ValidateQueryString

- ea: `0x62b0`
- end: `0x635d`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::ValidateQueryString`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6220`

## callees

- `0x3750`
- `0x39d0`
- `0x62b0`
- `0xb330`

## pseudocode

```c

```

## disassembly

```asm
0x62b0  ldc.i4.0
0x62b1  stloc.0
0x62b2  ldc.i4.0
0x62b3  stloc.1
0x62b4  br.s     loc_6324
0x62b6  ldarg.0
0x62b7  ldloc.1
0x62b8  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x62bd  stloc.2
0x62be  ldloc.2
0x62bf  ldc.i4.s 0x5B
0x62c1  beq.s    loc_62CA
0x62c3  ldloc.2
0x62c4  ldc.i4.s 0x5D
0x62c6  beq.s    loc_62F5
0x62c8  br.s     loc_6320
0x62ca  ldloc.0
0x62cb  brtrue.s loc_62D1
0x62cd  ldc.i4.1
0x62ce  stloc.0
0x62cf  br.s     loc_6320
0x62d1  ldarg.1
0x62d2  brfalse.s loc_62F3
0x62d4  call     string System.Net.Http.Properties.Resources::get_NestedBracketNotValid()
0x62d9  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x62de  ldc.i4.1
0x62df  newarr   [mscorlib]System.Object
0x62e4  dup
0x62e5  ldc.i4.0
0x62e6  ldloc.1
0x62e7  box      [mscorlib]System.Int32
0x62ec  stelem.ref
0x62ed  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x62f2  throw
0x62f3  ldc.i4.0
0x62f4  ret
0x62f5  ldloc.0
0x62f6  brfalse.s loc_62FC
0x62f8  ldc.i4.0
0x62f9  stloc.0
0x62fa  br.s     loc_6320
0x62fc  ldarg.1
0x62fd  brfalse.s loc_631E
0x62ff  call     string System.Net.Http.Properties.Resources::get_UnMatchedBracketNotValid()
0x6304  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x6309  ldc.i4.1
0x630a  newarr   [mscorlib]System.Object
0x630f  dup
0x6310  ldc.i4.0
0x6311  ldloc.1
0x6312  box      [mscorlib]System.Int32
0x6317  stelem.ref
0x6318  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x631d  throw
0x631e  ldc.i4.0
0x631f  ret
0x6320  ldloc.1
0x6321  ldc.i4.1
0x6322  add
0x6323  stloc.1
0x6324  ldloc.1
0x6325  ldarg.0
0x6326  callvirt instance int32 [mscorlib]System.String::get_Length()
0x632b  blt.s    loc_62B6
0x632d  ldloc.0
0x632e  brfalse.s loc_635B
0x6330  ldarg.1
0x6331  brfalse.s loc_6359
0x6333  call     string System.Net.Http.Properties.Resources::get_NestedBracketNotValid()
0x6338  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x633d  ldc.i4.1
0x633e  newarr   [mscorlib]System.Object
0x6343  dup
0x6344  ldc.i4.0
0x6345  ldarg.0
0x6346  ldc.i4.s 0x5B
0x6348  callvirt instance int32 [mscorlib]System.String::LastIndexOf(char)
0x634d  box      [mscorlib]System.Int32
0x6352  stelem.ref
0x6353  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string parameterName, string messageFormat, object[] messageArgs)
0x6358  throw
0x6359  ldc.i4.0
0x635a  ret
0x635b  ldc.i4.1
0x635c  ret
```
