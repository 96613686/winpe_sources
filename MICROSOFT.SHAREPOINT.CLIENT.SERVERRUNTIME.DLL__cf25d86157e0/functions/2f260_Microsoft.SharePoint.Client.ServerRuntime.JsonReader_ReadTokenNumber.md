# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenNumber

- ea: `0x2f260`
- end: `0x2f3ed`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenNumber`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ece0`

## callees

- `0x16f10`
- `0x179a0`
- `0x17b50`
- `0x2ec80`
- `0x2f050`
- `0x2f260`
- `0x30530`
- `0x30600`
- `0x30640`
- `0x30680`

## string_xrefs

- `0x2f29f`: `JsonNotWellFormated`
- `0x2f3c9`: `JsonUnknownData`

## pseudocode

```c

```

## disassembly

```asm
0x2f260  ldarg.0
0x2f261  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f266  ldarg.0
0x2f267  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tokenBuffer
0x2f26c  ldarg.0
0x2f26d  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tokenBuffer
0x2f272  ldlen
0x2f273  conv.i4
0x2f274  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Peek(char[] buffer, int32 count)
0x2f279  stloc.1
0x2f27a  ldc.i4.0
0x2f27b  stloc.2
0x2f27c  br.s     loc_2F294
0x2f27e  ldarg.0
0x2f27f  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tokenBuffer
0x2f284  ldloc.2
0x2f285  ldelem.u2
0x2f286  stloc.3
0x2f287  ldarg.0
0x2f288  ldloc.3
0x2f289  call     instance bool Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IsTokenEnd(int32 ch)
0x2f28e  brtrue.s loc_2F298
0x2f290  ldloc.2
0x2f291  ldc.i4.1
0x2f292  add
0x2f293  stloc.2
0x2f294  ldloc.2
0x2f295  ldloc.1
0x2f296  blt.s    loc_2F27E
0x2f298  ldloc.2
0x2f299  brfalse.s loc_2F29F
0x2f29b  ldloc.2
0x2f29c  ldloc.1
0x2f29d  bne.un.s loc_2F2C3
0x2f29f  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2f2a4  ldc.i4.1
0x2f2a5  newarr   [mscorlib]System.Object
0x2f2aa  stloc.s  9
0x2f2ac  ldloc.s  9
0x2f2ae  ldc.i4.0
0x2f2af  ldarg.1
0x2f2b0  box      [mscorlib]System.Int32
0x2f2b5  stelem.ref
0x2f2b6  ldloc.s  9
0x2f2b8  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f2bd  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f2c2  throw
0x2f2c3  ldarg.0
0x2f2c4  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tokenBuffer
0x2f2c9  ldc.i4.0
0x2f2ca  ldloc.2
0x2f2cb  newobj   instance void [mscorlib]System.String::.ctor(char[], int32, int32)
0x2f2d0  stloc.s  4
0x2f2d2  ldloc.s  4
0x2f2d4  ldc.i4.7
0x2f2d5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f2da  ldloca.s 5
0x2f2dc  call     bool [mscorlib]System.Int64::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int64&)
0x2f2e1  brfalse.s loc_2F308
0x2f2e3  ldc.i4.5
0x2f2e4  ldarg.1
0x2f2e5  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2f2ea  stloc.0
0x2f2eb  ldloc.0
0x2f2ec  ldloc.s  5
0x2f2ee  callvirt instance void Token::set_LongValue(int64 value)
0x2f2f3  ldarg.0
0x2f2f4  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f2f9  ldloc.2
0x2f2fa  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip(int32 count)
0x2f2ff  pop
0x2f300  ldarg.0
0x2f301  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2f306  ldloc.0
0x2f307  ret
0x2f308  ldloc.s  4
0x2f30a  ldc.i4.7
0x2f30b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f310  ldloca.s 6
0x2f312  call     bool [mscorlib]System.UInt64::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, unsigned int64&)
0x2f317  brfalse.s loc_2F33E
0x2f319  ldc.i4.6
0x2f31a  ldarg.1
0x2f31b  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2f320  stloc.0
0x2f321  ldloc.0
0x2f322  ldloc.s  6
0x2f324  callvirt instance void Token::set_ULongValue(unsigned int64 value)
0x2f329  ldarg.0
0x2f32a  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f32f  ldloc.2
0x2f330  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip(int32 count)
0x2f335  pop
0x2f336  ldarg.0
0x2f337  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2f33c  ldloc.0
0x2f33d  ret
0x2f33e  ldc.r8   0.0
0x2f347  stloc.s  7
0x2f349  ldc.i4.0
0x2f34a  stloc.s  8
0x2f34c  ldloc.s  4
0x2f34e  ldsfld   string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::MinDoubleValueAsString
0x2f353  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f358  brfalse.s loc_2F36A
0x2f35a  ldc.r8   -1.797693134862316e308
0x2f363  stloc.s  7
0x2f365  ldc.i4.1
0x2f366  stloc.s  8
0x2f368  br.s     loc_2F3A0
0x2f36a  ldloc.s  4
0x2f36c  ldsfld   string Microsoft.SharePoint.Client.ServerRuntime.JsonReader::MaxDoubleValueAsString
0x2f371  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f376  brfalse.s loc_2F388
0x2f378  ldc.r8   1.797693134862316e308
0x2f381  stloc.s  7
0x2f383  ldc.i4.1
0x2f384  stloc.s  8
0x2f386  br.s     loc_2F3A0
0x2f388  ldloc.s  4
0x2f38a  ldc.i4   0xA7
0x2f38f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f394  ldloca.s 7
0x2f396  call     bool [mscorlib]System.Double::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, float64&)
0x2f39b  brfalse.s loc_2F3A0
0x2f39d  ldc.i4.1
0x2f39e  stloc.s  8
0x2f3a0  ldloc.s  8
0x2f3a2  brfalse.s loc_2F3C9
0x2f3a4  ldc.i4.7
0x2f3a5  ldarg.1
0x2f3a6  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2f3ab  stloc.0
0x2f3ac  ldloc.0
0x2f3ad  ldloc.s  7
0x2f3af  callvirt instance void Token::set_DoubleValue(float64 value)
0x2f3b4  ldarg.0
0x2f3b5  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f3ba  ldloc.2
0x2f3bb  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip(int32 count)
0x2f3c0  pop
0x2f3c1  ldarg.0
0x2f3c2  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2f3c7  ldloc.0
0x2f3c8  ret
0x2f3c9  ldstr    aJsonunknowndat// "JsonUnknownData"
0x2f3ce  ldc.i4.1
0x2f3cf  newarr   [mscorlib]System.Object
0x2f3d4  stloc.s  0xA
0x2f3d6  ldloc.s  0xA
0x2f3d8  ldc.i4.0
0x2f3d9  ldarg.1
0x2f3da  box      [mscorlib]System.Int32
0x2f3df  stelem.ref
0x2f3e0  ldloc.s  0xA
0x2f3e2  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f3e7  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f3ec  throw
```
