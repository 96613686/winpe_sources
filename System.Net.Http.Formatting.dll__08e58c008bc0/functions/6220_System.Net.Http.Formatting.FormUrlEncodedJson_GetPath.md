# System.Net.Http.Formatting.FormUrlEncodedJson::GetPath

- ea: `0x6220`
- end: `0x62a6`
- name: `System.Net.Http.Formatting.FormUrlEncodedJson::GetPath`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6140`

## callees

- `0x3590`
- `0x6220`
- `0x62b0`
- `0xb320`

## pseudocode

```c

```

## disassembly

```asm
0x6220  ldarg.0
0x6221  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6226  brfalse.s loc_622E
0x6228  ldsfld   string[] System.Net.Http.Formatting.FormUrlEncodedJson::_emptyPath
0x622d  ret
0x622e  ldarg.0
0x622f  ldarg.2
0x6230  call     bool System.Net.Http.Formatting.FormUrlEncodedJson::ValidateQueryString(string key, bool throwOnError)
0x6235  brtrue.s loc_6239
0x6237  ldnull
0x6238  ret
0x6239  ldarg.0
0x623a  ldc.i4.1
0x623b  newarr   [mscorlib]System.Char
0x6240  dup
0x6241  ldc.i4.0
0x6242  ldc.i4.s 0x5B
0x6244  stelem.i2
0x6245  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x624a  stloc.0
0x624b  ldc.i4.0
0x624c  stloc.1
0x624d  br.s     loc_6279
0x624f  ldloc.0
0x6250  ldloc.1
0x6251  ldelem.ref
0x6252  ldstr    asc_10C74// "]"
0x6257  ldc.i4.4
0x6258  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x625d  brfalse.s loc_6275
0x625f  ldloc.0
0x6260  ldloc.1
0x6261  ldloc.0
0x6262  ldloc.1
0x6263  ldelem.ref
0x6264  ldc.i4.0
0x6265  ldloc.0
0x6266  ldloc.1
0x6267  ldelem.ref
0x6268  callvirt instance int32 [mscorlib]System.String::get_Length()
0x626d  ldc.i4.1
0x626e  sub
0x626f  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x6274  stelem.ref
0x6275  ldloc.1
0x6276  ldc.i4.1
0x6277  add
0x6278  stloc.1
0x6279  ldloc.1
0x627a  ldloc.0
0x627b  ldlen
0x627c  conv.i4
0x627d  blt.s    loc_624F
0x627f  ldloc.0
0x6280  ldlen
0x6281  conv.i4
0x6282  ldarg.1
0x6283  blt.s    loc_62A4
0x6285  ldarg.2
0x6286  brfalse.s loc_62A2
0x6288  call     string System.Net.Http.Properties.Resources::get_MaxDepthExceeded()
0x628d  ldc.i4.1
0x628e  newarr   [mscorlib]System.Object
0x6293  dup
0x6294  ldc.i4.0
0x6295  ldarg.1
0x6296  box      [mscorlib]System.Int32
0x629b  stelem.ref
0x629c  call     class [mscorlib]System.ArgumentException System.Web.Http.Error::Argument(string messageFormat, object[] messageArgs)
0x62a1  throw
0x62a2  ldnull
0x62a3  ret
0x62a4  ldloc.0
0x62a5  ret
```
