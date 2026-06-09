# <SkipDtdAsync>d__570::MoveNext

- ea: `0x108cf0`
- end: `0x109592`
- name: `<SkipDtdAsync>d__570::MoveNext`
- size: `2210`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x10e60`
- `0x29740`
- `0x313a0`
- `0x31500`
- `0x33200`
- `0x34d30`
- `0x34d80`
- `0x34dd0`
- `0x34ef0`
- `0xfeb70`
- `0x108cf0`

## string_xrefs

- `0x108ebe`: `Xml_UnexpectedEOF1`
- `0x1091f1`: `Xml_UnexpectedEOF1`
- `0x1093e4`: `Xml_ExpectExternalOrClose`
- `0x109549`: `Xml_ExpectSubOrClose`

## pseudocode

```c

```

## disassembly

```asm
0x108cf0  ldarg.0
0x108cf1  ldfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108cf6  stloc.0
0x108cf7  ldarg.0
0x108cf8  ldfld    class System.Xml.XmlTextReaderImpl <SkipDtdAsync>d__570::<>4__this
0x108cfd  stloc.1
0x108cfe  ldloc.0
0x108cff  switch   loc_108D80, loc_108E0A, loc_108E93, loc_108F68, loc_108FE7, loc_109050, loc_1090CF, loc_109138, loc_1091C6, loc_10929C, loc_10931C, loc_109386, loc_109464, loc_1094CE
0x108d3c  ldloc.1
0x108d3d  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, int32>> System.Xml.XmlTextReaderImpl::ParseQNameAsync()
0x108d42  ldc.i4.0
0x108d43  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Tuple`2<int32, int32>>::ConfigureAwait(!!T0)
0x108d48  stloc.s  7
0x108d4a  ldloca.s 7
0x108d4c  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<class [mscorlib]System.Tuple`2<int32, int32>>::GetAwaiter()
0x108d51  stloc.s  6
0x108d53  ldloca.s 6
0x108d55  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, int32>>::get_IsCompleted()
0x108d5a  brtrue.s loc_108D9D
0x108d5c  ldarg.0
0x108d5d  ldc.i4.0
0x108d5e  dup
0x108d5f  stloc.0
0x108d60  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108d65  ldarg.0
0x108d66  ldloc.s  6
0x108d68  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, int32>> <SkipDtdAsync>d__570::<>u__1
0x108d6d  ldarg.0
0x108d6e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SkipDtdAsync>d__570::<>t__builder
0x108d73  ldloca.s 6
0x108d75  ldarg.0
0x108d76  call     T0x2B000216
0x108d7b  leave    loc_109591
0x108d80  ldarg.0
0x108d81  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, int32>> <SkipDtdAsync>d__570::<>u__1
0x108d86  stloc.s  6
0x108d88  ldarg.0
0x108d89  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, int32>> <SkipDtdAsync>d__570::<>u__1
0x108d8e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, int32>>
0x108d94  ldarg.0
0x108d95  ldc.i4.m1
0x108d96  dup
0x108d97  stloc.0
0x108d98  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108d9d  ldloca.s 6
0x108d9f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<class [mscorlib]System.Tuple`2<int32, int32>>::GetResult()
0x108da4  stloc.s  5
0x108da6  ldloc.s  5
0x108da8  stloc.3
0x108da9  ldloc.3
0x108daa  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, int32>::get_Item1()
0x108daf  stloc.2
0x108db0  ldloc.3
0x108db1  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, int32>::get_Item2()
0x108db6  stloc.s  4
0x108db8  ldloc.1
0x108db9  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108dbe  ldloc.s  4
0x108dc0  stfld    int32 ParsingState::charPos
0x108dc5  ldloc.1
0x108dc6  ldnull
0x108dc7  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::EatWhitespacesAsync(class [mscorlib]System.Text.StringBuilder sb)
0x108dcc  ldc.i4.0
0x108dcd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x108dd2  stloc.s  9
0x108dd4  ldloca.s 9
0x108dd6  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x108ddb  stloc.s  8
0x108ddd  ldloca.s 8
0x108ddf  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x108de4  brtrue.s loc_108E27
0x108de6  ldarg.0
0x108de7  ldc.i4.1
0x108de8  dup
0x108de9  stloc.0
0x108dea  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108def  ldarg.0
0x108df0  ldloc.s  8
0x108df2  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108df7  ldarg.0
0x108df8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SkipDtdAsync>d__570::<>t__builder
0x108dfd  ldloca.s 8
0x108dff  ldarg.0
0x108e00  call     T0x2B000217
0x108e05  leave    loc_109591
0x108e0a  ldarg.0
0x108e0b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108e10  stloc.s  8
0x108e12  ldarg.0
0x108e13  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108e18  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x108e1e  ldarg.0
0x108e1f  ldc.i4.m1
0x108e20  dup
0x108e21  stloc.0
0x108e22  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108e27  ldloca.s 8
0x108e29  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x108e2e  pop
0x108e2f  ldloc.1
0x108e30  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108e35  ldfld    char[] ParsingState::chars
0x108e3a  ldloc.1
0x108e3b  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108e40  ldfld    int32 ParsingState::charPos
0x108e45  ldelem.u2
0x108e46  ldc.i4.s 0x50
0x108e48  bne.un   loc_109162
0x108e4d  br.s     loc_108EC8
0x108e4f  ldloc.1
0x108e50  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::ReadDataAsync()
0x108e55  ldc.i4.0
0x108e56  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x108e5b  stloc.s  9
0x108e5d  ldloca.s 9
0x108e5f  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x108e64  stloc.s  0xB
0x108e66  ldloca.s 0xB
0x108e68  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x108e6d  brtrue.s loc_108EB0
0x108e6f  ldarg.0
0x108e70  ldc.i4.2
0x108e71  dup
0x108e72  stloc.0
0x108e73  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108e78  ldarg.0
0x108e79  ldloc.s  0xB
0x108e7b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108e80  ldarg.0
0x108e81  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SkipDtdAsync>d__570::<>t__builder
0x108e86  ldloca.s 0xB
0x108e88  ldarg.0
0x108e89  call     T0x2B000217
0x108e8e  leave    loc_109591
0x108e93  ldarg.0
0x108e94  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108e99  stloc.s  0xB
0x108e9b  ldarg.0
0x108e9c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108ea1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x108ea7  ldarg.0
0x108ea8  ldc.i4.m1
0x108ea9  dup
0x108eaa  stloc.0
0x108eab  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108eb0  ldloca.s 0xB
0x108eb2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x108eb7  stloc.s  0xA
0x108eb9  ldloc.s  0xA
0x108ebb  brtrue.s loc_108EC8
0x108ebd  ldloc.1
0x108ebe  ldstr    aXmlUnexpectede_0// "Xml_UnexpectedEOF1"
0x108ec3  call     instance void System.Xml.XmlTextReaderImpl::Throw(string res)
0x108ec8  ldloc.1
0x108ec9  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108ece  ldfld    int32 ParsingState::charsUsed
0x108ed3  ldloc.1
0x108ed4  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108ed9  ldfld    int32 ParsingState::charPos
0x108ede  sub
0x108edf  ldc.i4.6
0x108ee0  blt      loc_108E4F
0x108ee5  ldloc.1
0x108ee6  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108eeb  ldfld    char[] ParsingState::chars
0x108ef0  ldloc.1
0x108ef1  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108ef6  ldfld    int32 ParsingState::charPos
0x108efb  ldc.i4.6
0x108efc  ldstr    aPublic_0// "PUBLIC"
0x108f01  call     bool System.Xml.XmlConvert::StrEqual(char[] chars, int32 strPos1, int32 strLen1, string str2)
0x108f06  brtrue.s loc_108F13
0x108f08  ldloc.1
0x108f09  ldstr    aPublic_0// "PUBLIC"
0x108f0e  call     instance void System.Xml.XmlTextReaderImpl::ThrowUnexpectedToken(string expectedToken1)
0x108f13  ldloc.1
0x108f14  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108f19  ldflda   int32 ParsingState::charPos
0x108f1e  dup
0x108f1f  ldind.i4
0x108f20  ldc.i4.6
0x108f21  add
0x108f22  stind.i4
0x108f23  ldloc.1
0x108f24  ldnull
0x108f25  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::EatWhitespacesAsync(class [mscorlib]System.Text.StringBuilder sb)
0x108f2a  ldc.i4.0
0x108f2b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x108f30  stloc.s  9
0x108f32  ldloca.s 9
0x108f34  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x108f39  stloc.s  0xD
0x108f3b  ldloca.s 0xD
0x108f3d  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x108f42  brtrue.s loc_108F85
0x108f44  ldarg.0
0x108f45  ldc.i4.3
0x108f46  dup
0x108f47  stloc.0
0x108f48  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108f4d  ldarg.0
0x108f4e  ldloc.s  0xD
0x108f50  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108f55  ldarg.0
0x108f56  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SkipDtdAsync>d__570::<>t__builder
0x108f5b  ldloca.s 0xD
0x108f5d  ldarg.0
0x108f5e  call     T0x2B000217
0x108f63  leave    loc_109591
0x108f68  ldarg.0
0x108f69  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108f6e  stloc.s  0xD
0x108f70  ldarg.0
0x108f71  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x108f76  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
0x108f7c  ldarg.0
0x108f7d  ldc.i4.m1
0x108f7e  dup
0x108f7f  stloc.0
0x108f80  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108f85  ldloca.s 0xD
0x108f87  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::GetResult()
0x108f8c  stloc.s  0xC
0x108f8e  ldloc.s  0xC
0x108f90  brtrue.s loc_108FA3
0x108f92  ldloc.1
0x108f93  ldloc.1
0x108f94  ldflda   valuetype ParsingState System.Xml.XmlTextReaderImpl::ps
0x108f99  ldfld    int32 ParsingState::charPos
0x108f9e  call     instance void System.Xml.XmlTextReaderImpl::ThrowExpectingWhitespace(int32 pos)
0x108fa3  ldloc.1
0x108fa4  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlTextReaderImpl::SkipPublicOrSystemIdLiteralAsync()
0x108fa9  ldc.i4.0
0x108faa  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x108faf  stloc.s  0xF
0x108fb1  ldloca.s 0xF
0x108fb3  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x108fb8  stloc.s  0xE
0x108fba  ldloca.s 0xE
0x108fbc  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x108fc1  brtrue.s loc_109004
0x108fc3  ldarg.0
0x108fc4  ldc.i4.4
0x108fc5  dup
0x108fc6  stloc.0
0x108fc7  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x108fcc  ldarg.0
0x108fcd  ldloc.s  0xE
0x108fcf  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SkipDtdAsync>d__570::<>u__3
0x108fd4  ldarg.0
0x108fd5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SkipDtdAsync>d__570::<>t__builder
0x108fda  ldloca.s 0xE
0x108fdc  ldarg.0
0x108fdd  call     T0x2B000218
0x108fe2  leave    loc_109591
0x108fe7  ldarg.0
0x108fe8  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SkipDtdAsync>d__570::<>u__3
0x108fed  stloc.s  0xE
0x108fef  ldarg.0
0x108ff0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <SkipDtdAsync>d__570::<>u__3
0x108ff5  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x108ffb  ldarg.0
0x108ffc  ldc.i4.m1
0x108ffd  dup
0x108ffe  stloc.0
0x108fff  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x109004  ldloca.s 0xE
0x109006  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x10900b  ldloc.1
0x10900c  ldnull
0x10900d  call     instance class [mscorlib]System.Threading.Tasks.Task`1<int32> System.Xml.XmlTextReaderImpl::EatWhitespacesAsync(class [mscorlib]System.Text.StringBuilder sb)
0x109012  ldc.i4.0
0x109013  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::ConfigureAwait(!!T0)
0x109018  stloc.s  9
0x10901a  ldloca.s 9
0x10901c  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<int32>::GetAwaiter()
0x109021  stloc.s  0x11
0x109023  ldloca.s 0x11
0x109025  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>::get_IsCompleted()
0x10902a  brtrue.s loc_10906D
0x10902c  ldarg.0
0x10902d  ldc.i4.5
0x10902e  dup
0x10902f  stloc.0
0x109030  stfld    int32 <SkipDtdAsync>d__570::<>1__state
0x109035  ldarg.0
0x109036  ldloc.s  0x11
0x109038  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x10903d  ldarg.0
0x10903e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SkipDtdAsync>d__570::<>t__builder
0x109043  ldloca.s 0x11
0x109045  ldarg.0
0x109046  call     T0x2B000217
0x10904b  leave    loc_109591
0x109050  ldarg.0
0x109051  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x109056  stloc.s  0x11
0x109058  ldarg.0
0x109059  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32> <SkipDtdAsync>d__570::<>u__2
0x10905e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<int32>
  ... truncated ...
```
