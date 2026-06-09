# <ScanQNameAsync>d__198::MoveNext

- ea: `0x121a40`
- end: `0x121d0c`
- name: `<ScanQNameAsync>d__198::MoveNext`
- size: `716`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x12920`
- `0x12940`
- `0x60df0`
- `0x60e40`
- `0x61c30`
- `0x121a40`

## string_xrefs

- `0x121aca`: `Xml_BadStartNameChar`
- `0x121bcd`: `Xml_BadNameChar`
- `0x121b67`: `Xml_UnexpectedEOF`
- `0x121caf`: `Xml_UnexpectedEOF`

## pseudocode

```c

```

## disassembly

```asm
0x121a40  ldarg.0
0x121a41  ldfld    int32 <ScanQNameAsync>d__198::<>1__state
0x121a46  stloc.0
0x121a47  ldarg.0
0x121a48  ldfld    class System.Xml.DtdParser <ScanQNameAsync>d__198::<>4__this
0x121a4d  stloc.1
0x121a4e  ldloc.0
0x121a4f  brfalse  loc_121B35
0x121a54  ldloc.0
0x121a55  ldc.i4.1
0x121a56  beq      loc_121C6D
0x121a5b  ldloc.1
0x121a5c  ldloc.1
0x121a5d  ldfld    int32 System.Xml.DtdParser::curPos
0x121a62  stfld    int32 System.Xml.DtdParser::tokenStartPos
0x121a67  ldarg.0
0x121a68  ldc.i4.m1
0x121a69  stfld    int32 <ScanQNameAsync>d__198::<colonOffset>5__2
0x121a6e  ldc.i4.0
0x121a6f  stloc.2
0x121a70  ldloc.1
0x121a71  ldflda   valuetype System.Xml.XmlCharType System.Xml.DtdParser::xmlCharType
0x121a76  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x121a7b  ldloc.1
0x121a7c  ldfld    char[] System.Xml.DtdParser::chars
0x121a81  ldloc.1
0x121a82  ldfld    int32 System.Xml.DtdParser::curPos
0x121a87  ldelem.u2
0x121a88  add
0x121a89  ldind.u1
0x121a8a  ldc.i4.4
0x121a8b  and
0x121a8c  brtrue.s loc_121A9F
0x121a8e  ldloc.1
0x121a8f  ldfld    char[] System.Xml.DtdParser::chars
0x121a94  ldloc.1
0x121a95  ldfld    int32 System.Xml.DtdParser::curPos
0x121a9a  ldelem.u2
0x121a9b  ldc.i4.s 0x3A
0x121a9d  bne.un.s loc_121AAF
0x121a9f  ldloc.1
0x121aa0  ldloc.1
0x121aa1  ldfld    int32 System.Xml.DtdParser::curPos
0x121aa6  ldc.i4.1
0x121aa7  add
0x121aa8  stfld    int32 System.Xml.DtdParser::curPos
0x121aad  br.s     loc_121AEB
0x121aaf  ldloc.1
0x121ab0  ldfld    int32 System.Xml.DtdParser::curPos
0x121ab5  ldc.i4.1
0x121ab6  add
0x121ab7  ldloc.1
0x121ab8  ldfld    int32 System.Xml.DtdParser::charsUsed
0x121abd  blt.s    loc_121AC3
0x121abf  ldc.i4.1
0x121ac0  stloc.2
0x121ac1  br.s     loc_121AEB
0x121ac3  ldloc.1
0x121ac4  ldloc.1
0x121ac5  ldfld    int32 System.Xml.DtdParser::curPos
0x121aca  ldstr    aXmlBadstartnam// "Xml_BadStartNameChar"
0x121acf  ldloc.1
0x121ad0  ldfld    char[] System.Xml.DtdParser::chars
0x121ad5  ldloc.1
0x121ad6  ldfld    int32 System.Xml.DtdParser::charsUsed
0x121adb  ldloc.1
0x121adc  ldfld    int32 System.Xml.DtdParser::curPos
0x121ae1  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char[] data, int32 length, int32 invCharIndex)
0x121ae6  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string[] args)
0x121aeb  ldloc.2
0x121aec  brfalse  loc_121B76
0x121af1  ldloc.1
0x121af2  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.DtdParser::ReadDataInNameAsync()
0x121af7  ldc.i4.0
0x121af8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x121afd  stloc.s  5
0x121aff  ldloca.s 5
0x121b01  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x121b06  stloc.s  4
0x121b08  ldloca.s 4
0x121b0a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x121b0f  brtrue.s loc_121B52
0x121b11  ldarg.0
0x121b12  ldc.i4.0
0x121b13  dup
0x121b14  stloc.0
0x121b15  stfld    int32 <ScanQNameAsync>d__198::<>1__state
0x121b1a  ldarg.0
0x121b1b  ldloc.s  4
0x121b1d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ScanQNameAsync>d__198::<>u__1
0x121b22  ldarg.0
0x121b23  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ScanQNameAsync>d__198::<>t__builder
0x121b28  ldloca.s 4
0x121b2a  ldarg.0
0x121b2b  call     T0x2B0002D6
0x121b30  leave    loc_121D0B
0x121b35  ldarg.0
0x121b36  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ScanQNameAsync>d__198::<>u__1
0x121b3b  stloc.s  4
0x121b3d  ldarg.0
0x121b3e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ScanQNameAsync>d__198::<>u__1
0x121b43  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x121b49  ldarg.0
0x121b4a  ldc.i4.m1
0x121b4b  dup
0x121b4c  stloc.0
0x121b4d  stfld    int32 <ScanQNameAsync>d__198::<>1__state
0x121b52  ldloca.s 4
0x121b54  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x121b59  stloc.3
0x121b5a  ldloc.3
0x121b5b  brtrue   loc_121A6E
0x121b60  ldloc.1
0x121b61  ldloc.1
0x121b62  ldfld    int32 System.Xml.DtdParser::curPos
0x121b67  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x121b6c  ldstr    aName_0// "Name"
0x121b71  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x121b76  ldloc.1
0x121b77  ldflda   valuetype System.Xml.XmlCharType System.Xml.DtdParser::xmlCharType
0x121b7c  ldfld    unsigned int8* System.Xml.XmlCharType::charProperties
0x121b81  ldloc.1
0x121b82  ldfld    char[] System.Xml.DtdParser::chars
0x121b87  ldloc.1
0x121b88  ldfld    int32 System.Xml.DtdParser::curPos
0x121b8d  ldelem.u2
0x121b8e  add
0x121b8f  ldind.u1
0x121b90  ldc.i4.8
0x121b91  and
0x121b92  brfalse.s loc_121BA4
0x121b94  ldloc.1
0x121b95  ldloc.1
0x121b96  ldfld    int32 System.Xml.DtdParser::curPos
0x121b9b  ldc.i4.1
0x121b9c  add
0x121b9d  stfld    int32 System.Xml.DtdParser::curPos
0x121ba2  br.s     loc_121B76
0x121ba4  ldloc.1
0x121ba5  ldfld    char[] System.Xml.DtdParser::chars
0x121baa  ldloc.1
0x121bab  ldfld    int32 System.Xml.DtdParser::curPos
0x121bb0  ldelem.u2
0x121bb1  ldc.i4.s 0x3A
0x121bb3  bne.un.s loc_121C18
0x121bb5  ldarg.0
0x121bb6  ldfld    bool <ScanQNameAsync>d__198::isQName
0x121bbb  brfalse.s loc_121C05
0x121bbd  ldarg.0
0x121bbe  ldfld    int32 <ScanQNameAsync>d__198::<colonOffset>5__2
0x121bc3  ldc.i4.m1
0x121bc4  beq.s    loc_121BDF
0x121bc6  ldloc.1
0x121bc7  ldloc.1
0x121bc8  ldfld    int32 System.Xml.DtdParser::curPos
0x121bcd  ldstr    aXmlBadnamechar// "Xml_BadNameChar"
0x121bd2  ldc.i4.s 0x3A
0x121bd4  ldc.i4.0
0x121bd5  call     string[] System.Xml.XmlException::BuildCharExceptionArgs(char invChar, char nextChar)
0x121bda  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string[] args)
0x121bdf  ldarg.0
0x121be0  ldloc.1
0x121be1  ldfld    int32 System.Xml.DtdParser::curPos
0x121be6  ldloc.1
0x121be7  ldfld    int32 System.Xml.DtdParser::tokenStartPos
0x121bec  sub
0x121bed  stfld    int32 <ScanQNameAsync>d__198::<colonOffset>5__2
0x121bf2  ldloc.1
0x121bf3  ldloc.1
0x121bf4  ldfld    int32 System.Xml.DtdParser::curPos
0x121bf9  ldc.i4.1
0x121bfa  add
0x121bfb  stfld    int32 System.Xml.DtdParser::curPos
0x121c00  br       loc_121A6E
0x121c05  ldloc.1
0x121c06  ldloc.1
0x121c07  ldfld    int32 System.Xml.DtdParser::curPos
0x121c0c  ldc.i4.1
0x121c0d  add
0x121c0e  stfld    int32 System.Xml.DtdParser::curPos
0x121c13  br       loc_121B76
0x121c18  ldloc.1
0x121c19  ldfld    int32 System.Xml.DtdParser::curPos
0x121c1e  ldloc.1
0x121c1f  ldfld    int32 System.Xml.DtdParser::charsUsed
0x121c24  bne.un   loc_121CBE
0x121c29  ldloc.1
0x121c2a  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.DtdParser::ReadDataInNameAsync()
0x121c2f  ldc.i4.0
0x121c30  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x121c35  stloc.s  5
0x121c37  ldloca.s 5
0x121c39  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x121c3e  stloc.s  7
0x121c40  ldloca.s 7
0x121c42  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x121c47  brtrue.s loc_121C8A
0x121c49  ldarg.0
0x121c4a  ldc.i4.1
0x121c4b  dup
0x121c4c  stloc.0
0x121c4d  stfld    int32 <ScanQNameAsync>d__198::<>1__state
0x121c52  ldarg.0
0x121c53  ldloc.s  7
0x121c55  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ScanQNameAsync>d__198::<>u__1
0x121c5a  ldarg.0
0x121c5b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ScanQNameAsync>d__198::<>t__builder
0x121c60  ldloca.s 7
0x121c62  ldarg.0
0x121c63  call     T0x2B0002D6
0x121c68  leave    loc_121D0B
0x121c6d  ldarg.0
0x121c6e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ScanQNameAsync>d__198::<>u__1
0x121c73  stloc.s  7
0x121c75  ldarg.0
0x121c76  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <ScanQNameAsync>d__198::<>u__1
0x121c7b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x121c81  ldarg.0
0x121c82  ldc.i4.m1
0x121c83  dup
0x121c84  stloc.0
0x121c85  stfld    int32 <ScanQNameAsync>d__198::<>1__state
0x121c8a  ldloca.s 7
0x121c8c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x121c91  stloc.s  6
0x121c93  ldloc.s  6
0x121c95  brtrue   loc_121B76
0x121c9a  ldloc.1
0x121c9b  ldfld    int32 System.Xml.DtdParser::tokenStartPos
0x121ca0  ldloc.1
0x121ca1  ldfld    int32 System.Xml.DtdParser::curPos
0x121ca6  bne.un.s loc_121CBE
0x121ca8  ldloc.1
0x121ca9  ldloc.1
0x121caa  ldfld    int32 System.Xml.DtdParser::curPos
0x121caf  ldstr    aXmlUnexpectede// "Xml_UnexpectedEOF"
0x121cb4  ldstr    aName_0// "Name"
0x121cb9  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x121cbe  ldloc.1
0x121cbf  ldarg.0
0x121cc0  ldfld    int32 <ScanQNameAsync>d__198::<colonOffset>5__2
0x121cc5  ldc.i4.m1
0x121cc6  beq.s    loc_121CD7
0x121cc8  ldloc.1
0x121cc9  ldfld    int32 System.Xml.DtdParser::tokenStartPos
0x121cce  ldarg.0
0x121ccf  ldfld    int32 <ScanQNameAsync>d__198::<colonOffset>5__2
0x121cd4  add
0x121cd5  br.s     loc_121CD8
0x121cd7  ldc.i4.m1
0x121cd8  stfld    int32 System.Xml.DtdParser::colonPos
0x121cdd  leave.s  loc_121CF8
0x121cdf  stloc.s  8
0x121ce1  ldarg.0
0x121ce2  ldc.i4.s 0xFE
0x121ce4  stfld    int32 <ScanQNameAsync>d__198::<>1__state
0x121ce9  ldarg.0
0x121cea  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ScanQNameAsync>d__198::<>t__builder
0x121cef  ldloc.s  8
0x121cf1  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x121cf6  leave.s  loc_121D0B
0x121cf8  ldarg.0
0x121cf9  ldc.i4.s 0xFE
0x121cfb  stfld    int32 <ScanQNameAsync>d__198::<>1__state
0x121d00  ldarg.0
0x121d01  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ScanQNameAsync>d__198::<>t__builder
0x121d06  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x121d0b  ret
```
