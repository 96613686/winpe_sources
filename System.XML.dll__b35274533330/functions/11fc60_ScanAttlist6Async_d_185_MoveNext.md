# <ScanAttlist6Async>d__185::MoveNext

- ea: `0x11fc60`
- end: `0x120022`
- name: `<ScanAttlist6Async>d__185::MoveNext`
- size: `962`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x60de0`
- `0x61950`
- `0x61d30`
- `0x11fc60`

## string_xrefs

- `0x11ffe5`: `Xml_IncompleteDtdContent`
- `0x11fdf4`: `Xml_ExpectAttType`
- `0x11fea9`: `Xml_ExpectAttType`
- `0x11ff24`: `Xml_ExpectAttType`
- `0x11ff53`: `Xml_ExpectAttType`
- `0x11ff66`: `Xml_ExpectAttType`

## pseudocode

```c

```

## disassembly

```asm
0x11fc60  ldarg.0
0x11fc61  ldfld    int32 <ScanAttlist6Async>d__185::<>1__state
0x11fc66  stloc.0
0x11fc67  ldarg.0
0x11fc68  ldfld    class System.Xml.DtdParser <ScanAttlist6Async>d__185::<>4__this
0x11fc6d  stloc.1
0x11fc6e  ldloc.0
0x11fc6f  brfalse.s loc_11FCE0
0x11fc71  ldloc.0
0x11fc72  ldc.i4.1
0x11fc73  beq      loc_11FFB1
0x11fc78  ldloc.1
0x11fc79  ldfld    char[] System.Xml.DtdParser::chars
0x11fc7e  ldloc.1
0x11fc7f  ldfld    int32 System.Xml.DtdParser::curPos
0x11fc84  ldelem.u2
0x11fc85  stloc.3
0x11fc86  ldloc.3
0x11fc87  ldc.i4.s 0x22
0x11fc89  beq.s    loc_11FC9B
0x11fc8b  ldloc.3
0x11fc8c  ldc.i4.s 0x23
0x11fc8e  beq      loc_11FD15
0x11fc93  ldloc.3
0x11fc94  ldc.i4.s 0x27
0x11fc96  bne.un   loc_11FF5F
0x11fc9b  ldloc.1
0x11fc9c  ldc.i4.0
0x11fc9d  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::ScanLiteralAsync(valuetype LiteralType literalType)
0x11fca2  ldc.i4.0
0x11fca3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11fca8  stloc.s  5
0x11fcaa  ldloca.s 5
0x11fcac  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11fcb1  stloc.s  4
0x11fcb3  ldloca.s 4
0x11fcb5  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11fcba  brtrue.s loc_11FCFD
0x11fcbc  ldarg.0
0x11fcbd  ldc.i4.0
0x11fcbe  dup
0x11fcbf  stloc.0
0x11fcc0  stfld    int32 <ScanAttlist6Async>d__185::<>1__state
0x11fcc5  ldarg.0
0x11fcc6  ldloc.s  4
0x11fcc8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ScanAttlist6Async>d__185::<>u__1
0x11fccd  ldarg.0
0x11fcce  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype Token> <ScanAttlist6Async>d__185::<>t__builder
0x11fcd3  ldloca.s 4
0x11fcd5  ldarg.0
0x11fcd6  call     T0x2B0002C8
0x11fcdb  leave    loc_120021
0x11fce0  ldarg.0
0x11fce1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ScanAttlist6Async>d__185::<>u__1
0x11fce6  stloc.s  4
0x11fce8  ldarg.0
0x11fce9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <ScanAttlist6Async>d__185::<>u__1
0x11fcee  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>
0x11fcf4  ldarg.0
0x11fcf5  ldc.i4.m1
0x11fcf6  dup
0x11fcf7  stloc.0
0x11fcf8  stfld    int32 <ScanAttlist6Async>d__185::<>1__state
0x11fcfd  ldloca.s 4
0x11fcff  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::GetResult()
0x11fd04  pop
0x11fd05  ldloc.1
0x11fd06  ldc.i4.s 0xD
0x11fd08  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11fd0d  ldc.i4.s 0x23
0x11fd0f  stloc.2
0x11fd10  leave    loc_12000D
0x11fd15  ldloc.1
0x11fd16  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11fd1b  ldloc.1
0x11fd1c  ldfld    int32 System.Xml.DtdParser::curPos
0x11fd21  sub
0x11fd22  ldc.i4.6
0x11fd23  blt      loc_11FF70
0x11fd28  ldloc.1
0x11fd29  ldfld    char[] System.Xml.DtdParser::chars
0x11fd2e  ldloc.1
0x11fd2f  ldfld    int32 System.Xml.DtdParser::curPos
0x11fd34  ldc.i4.1
0x11fd35  add
0x11fd36  ldelem.u2
0x11fd37  stloc.s  6
0x11fd39  ldloc.s  6
0x11fd3b  ldc.i4.s 0x46
0x11fd3d  beq      loc_11FED1
0x11fd42  ldloc.s  6
0x11fd44  ldc.i4.s 0x49
0x11fd46  beq      loc_11FE1D
0x11fd4b  ldloc.s  6
0x11fd4d  ldc.i4.s 0x52
0x11fd4f  bne.un   loc_11FF4C
0x11fd54  ldloc.1
0x11fd55  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11fd5a  ldloc.1
0x11fd5b  ldfld    int32 System.Xml.DtdParser::curPos
0x11fd60  sub
0x11fd61  ldc.i4.s 9
0x11fd63  blt      loc_11FF70
0x11fd68  ldloc.1
0x11fd69  ldfld    char[] System.Xml.DtdParser::chars
0x11fd6e  ldloc.1
0x11fd6f  ldfld    int32 System.Xml.DtdParser::curPos
0x11fd74  ldc.i4.2
0x11fd75  add
0x11fd76  ldelem.u2
0x11fd77  ldc.i4.s 0x45
0x11fd79  bne.un.s loc_11FDED
0x11fd7b  ldloc.1
0x11fd7c  ldfld    char[] System.Xml.DtdParser::chars
0x11fd81  ldloc.1
0x11fd82  ldfld    int32 System.Xml.DtdParser::curPos
0x11fd87  ldc.i4.3
0x11fd88  add
0x11fd89  ldelem.u2
0x11fd8a  ldc.i4.s 0x51
0x11fd8c  bne.un.s loc_11FDED
0x11fd8e  ldloc.1
0x11fd8f  ldfld    char[] System.Xml.DtdParser::chars
0x11fd94  ldloc.1
0x11fd95  ldfld    int32 System.Xml.DtdParser::curPos
0x11fd9a  ldc.i4.4
0x11fd9b  add
0x11fd9c  ldelem.u2
0x11fd9d  ldc.i4.s 0x55
0x11fd9f  bne.un.s loc_11FDED
0x11fda1  ldloc.1
0x11fda2  ldfld    char[] System.Xml.DtdParser::chars
0x11fda7  ldloc.1
0x11fda8  ldfld    int32 System.Xml.DtdParser::curPos
0x11fdad  ldc.i4.5
0x11fdae  add
0x11fdaf  ldelem.u2
0x11fdb0  ldc.i4.s 0x49
0x11fdb2  bne.un.s loc_11FDED
0x11fdb4  ldloc.1
0x11fdb5  ldfld    char[] System.Xml.DtdParser::chars
0x11fdba  ldloc.1
0x11fdbb  ldfld    int32 System.Xml.DtdParser::curPos
0x11fdc0  ldc.i4.6
0x11fdc1  add
0x11fdc2  ldelem.u2
0x11fdc3  ldc.i4.s 0x52
0x11fdc5  bne.un.s loc_11FDED
0x11fdc7  ldloc.1
0x11fdc8  ldfld    char[] System.Xml.DtdParser::chars
0x11fdcd  ldloc.1
0x11fdce  ldfld    int32 System.Xml.DtdParser::curPos
0x11fdd3  ldc.i4.7
0x11fdd4  add
0x11fdd5  ldelem.u2
0x11fdd6  ldc.i4.s 0x45
0x11fdd8  bne.un.s loc_11FDED
0x11fdda  ldloc.1
0x11fddb  ldfld    char[] System.Xml.DtdParser::chars
0x11fde0  ldloc.1
0x11fde1  ldfld    int32 System.Xml.DtdParser::curPos
0x11fde6  ldc.i4.8
0x11fde7  add
0x11fde8  ldelem.u2
0x11fde9  ldc.i4.s 0x44
0x11fdeb  beq.s    loc_11FDFE
0x11fded  ldloc.1
0x11fdee  ldloc.1
0x11fdef  ldfld    int32 System.Xml.DtdParser::curPos
0x11fdf4  ldstr    aXmlExpectattty// "Xml_ExpectAttType"
0x11fdf9  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11fdfe  ldloc.1
0x11fdff  ldloc.1
0x11fe00  ldfld    int32 System.Xml.DtdParser::curPos
0x11fe05  ldc.i4.s 9
0x11fe07  add
0x11fe08  stfld    int32 System.Xml.DtdParser::curPos
0x11fe0d  ldloc.1
0x11fe0e  ldc.i4.s 0xD
0x11fe10  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11fe15  ldc.i4.s 0x14
0x11fe17  stloc.2
0x11fe18  leave    loc_12000D
0x11fe1d  ldloc.1
0x11fe1e  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11fe23  ldloc.1
0x11fe24  ldfld    int32 System.Xml.DtdParser::curPos
0x11fe29  sub
0x11fe2a  ldc.i4.8
0x11fe2b  blt      loc_11FF70
0x11fe30  ldloc.1
0x11fe31  ldfld    char[] System.Xml.DtdParser::chars
0x11fe36  ldloc.1
0x11fe37  ldfld    int32 System.Xml.DtdParser::curPos
0x11fe3c  ldc.i4.2
0x11fe3d  add
0x11fe3e  ldelem.u2
0x11fe3f  ldc.i4.s 0x4D
0x11fe41  bne.un.s loc_11FEA2
0x11fe43  ldloc.1
0x11fe44  ldfld    char[] System.Xml.DtdParser::chars
0x11fe49  ldloc.1
0x11fe4a  ldfld    int32 System.Xml.DtdParser::curPos
0x11fe4f  ldc.i4.3
0x11fe50  add
0x11fe51  ldelem.u2
0x11fe52  ldc.i4.s 0x50
0x11fe54  bne.un.s loc_11FEA2
0x11fe56  ldloc.1
0x11fe57  ldfld    char[] System.Xml.DtdParser::chars
0x11fe5c  ldloc.1
0x11fe5d  ldfld    int32 System.Xml.DtdParser::curPos
0x11fe62  ldc.i4.4
0x11fe63  add
0x11fe64  ldelem.u2
0x11fe65  ldc.i4.s 0x4C
0x11fe67  bne.un.s loc_11FEA2
0x11fe69  ldloc.1
0x11fe6a  ldfld    char[] System.Xml.DtdParser::chars
0x11fe6f  ldloc.1
0x11fe70  ldfld    int32 System.Xml.DtdParser::curPos
0x11fe75  ldc.i4.5
0x11fe76  add
0x11fe77  ldelem.u2
0x11fe78  ldc.i4.s 0x49
0x11fe7a  bne.un.s loc_11FEA2
0x11fe7c  ldloc.1
0x11fe7d  ldfld    char[] System.Xml.DtdParser::chars
0x11fe82  ldloc.1
0x11fe83  ldfld    int32 System.Xml.DtdParser::curPos
0x11fe88  ldc.i4.6
0x11fe89  add
0x11fe8a  ldelem.u2
0x11fe8b  ldc.i4.s 0x45
0x11fe8d  bne.un.s loc_11FEA2
0x11fe8f  ldloc.1
0x11fe90  ldfld    char[] System.Xml.DtdParser::chars
0x11fe95  ldloc.1
0x11fe96  ldfld    int32 System.Xml.DtdParser::curPos
0x11fe9b  ldc.i4.7
0x11fe9c  add
0x11fe9d  ldelem.u2
0x11fe9e  ldc.i4.s 0x44
0x11fea0  beq.s    loc_11FEB3
0x11fea2  ldloc.1
0x11fea3  ldloc.1
0x11fea4  ldfld    int32 System.Xml.DtdParser::curPos
0x11fea9  ldstr    aXmlExpectattty// "Xml_ExpectAttType"
0x11feae  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res)
0x11feb3  ldloc.1
0x11feb4  ldloc.1
0x11feb5  ldfld    int32 System.Xml.DtdParser::curPos
0x11feba  ldc.i4.8
0x11febb  add
0x11febc  stfld    int32 System.Xml.DtdParser::curPos
0x11fec1  ldloc.1
0x11fec2  ldc.i4.s 0xD
0x11fec4  stfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11fec9  ldc.i4.s 0x15
0x11fecb  stloc.2
0x11fecc  leave    loc_12000D
0x11fed1  ldloc.1
0x11fed2  ldfld    char[] System.Xml.DtdParser::chars
0x11fed7  ldloc.1
0x11fed8  ldfld    int32 System.Xml.DtdParser::curPos
0x11fedd  ldc.i4.2
0x11fede  add
0x11fedf  ldelem.u2
0x11fee0  ldc.i4.s 0x49
0x11fee2  bne.un.s loc_11FF1D
0x11fee4  ldloc.1
0x11fee5  ldfld    char[] System.Xml.DtdParser::chars
0x11feea  ldloc.1
0x11feeb  ldfld    int32 System.Xml.DtdParser::curPos
0x11fef0  ldc.i4.3
0x11fef1  add
0x11fef2  ldelem.u2
0x11fef3  ldc.i4.s 0x58
0x11fef5  bne.un.s loc_11FF1D
0x11fef7  ldloc.1
0x11fef8  ldfld    char[] System.Xml.DtdParser::chars
0x11fefd  ldloc.1
0x11fefe  ldfld    int32 System.Xml.DtdParser::curPos
0x11ff03  ldc.i4.4
0x11ff04  add
0x11ff05  ldelem.u2
0x11ff06  ldc.i4.s 0x45
0x11ff08  bne.un.s loc_11FF1D
0x11ff0a  ldloc.1
0x11ff0b  ldfld    char[] System.Xml.DtdParser::chars
0x11ff10  ldloc.1
0x11ff11  ldfld    int32 System.Xml.DtdParser::curPos
0x11ff16  ldc.i4.5
0x11ff17  add
0x11ff18  ldelem.u2
0x11ff19  ldc.i4.s 0x44
0x11ff1b  beq.s    loc_11FF2E
0x11ff1d  ldloc.1
0x11ff1e  ldloc.1
0x11ff1f  ldfld    int32 System.Xml.DtdParser::curPos
  ... truncated ...
```
