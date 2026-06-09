# Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::GetArguments

- ea: `0x16ba30`
- end: `0x16bcb3`
- name: `Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::GetArguments`
- size: `643`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1698a0`
- `0x169ea0`
- `0x16a490`
- `0x16aa20`
- `0x16ade0`
- `0x16aed0`

## callees

- `0x16ba30`
- `0x1767c0`
- `0x232c60`
- `0x232c70`
- `0x232c80`

## string_xrefs

- `0x16ba7e`: `${openParen}`
- `0x16ba98`: `${comma}`
- `0x16baa5`: `${openCurly}`

## pseudocode

```c

```

## disassembly

```asm
0x16ba30  ldc.i4.1
0x16ba31  stloc.0
0x16ba32  ldc.i4.0
0x16ba33  stloc.1
0x16ba34  ldarg.s  4
0x16ba36  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x16ba3b  stind.ref
0x16ba3c  ldsfld   string [mscorlib]System.String::Empty
0x16ba41  stloc.2
0x16ba42  br       loc_16BC4A
0x16ba47  ldarg.0
0x16ba48  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x16ba4d  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::Arguments
0x16ba52  ldarg.2
0x16ba53  ldarg.1
0x16ba54  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, int32)
0x16ba59  stloc.3
0x16ba5a  ldloc.3
0x16ba5b  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x16ba60  brtrue.s loc_16BA7D
0x16ba62  ldloc.2
0x16ba63  ldarg.2
0x16ba64  ldarg.1
0x16ba65  callvirt instance string [mscorlib]System.String::Substring(int32)
0x16ba6a  call     string [mscorlib]System.String::Concat(string, string)
0x16ba6f  stloc.2
0x16ba70  ldarg.2
0x16ba71  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16ba76  starg.s  1
0x16ba78  br       loc_16BC4A
0x16ba7d  ldloc.3
0x16ba7e  ldstr    aOpenparen// "${openParen}"
0x16ba83  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x16ba88  stloc.s  4
0x16ba8a  ldloc.3
0x16ba8b  ldstr    aCloseparen// "${closeParen}"
0x16ba90  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x16ba95  stloc.s  5
0x16ba97  ldloc.3
0x16ba98  ldstr    aComma// "${comma}"
0x16ba9d  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x16baa2  stloc.s  6
0x16baa4  ldloc.3
0x16baa5  ldstr    aOpencurly// "${openCurly}"
0x16baaa  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x16baaf  stloc.s  7
0x16bab1  ldloc.3
0x16bab2  ldstr    aClosecurly// "${closeCurly}"
0x16bab7  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x16babc  stloc.s  8
0x16babe  ldloc.s  4
0x16bac0  brfalse.s loc_16BAF1
0x16bac2  ldloc.s  4
0x16bac4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16bac9  brfalse.s loc_16BAF1
0x16bacb  ldloc.0
0x16bacc  ldc.i4.1
0x16bacd  add
0x16bace  stloc.0
0x16bacf  ldloc.2
0x16bad0  ldarg.2
0x16bad1  ldarg.1
0x16bad2  ldloc.3
0x16bad3  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bad8  ldarg.1
0x16bad9  sub
0x16bada  ldloc.3
0x16badb  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x16bae0  add
0x16bae1  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16bae6  call     string [mscorlib]System.String::Concat(string, string)
0x16baeb  stloc.2
0x16baec  br       loc_16BC3B
0x16baf1  ldloc.s  5
0x16baf3  brfalse.s loc_16BB61
0x16baf5  ldloc.s  5
0x16baf7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16bafc  brfalse.s loc_16BB61
0x16bafe  ldloc.0
0x16baff  ldc.i4.1
0x16bb00  sub
0x16bb01  stloc.0
0x16bb02  ldloc.0
0x16bb03  brtrue.s loc_16BB3F
0x16bb05  ldloc.2
0x16bb06  ldarg.2
0x16bb07  ldarg.1
0x16bb08  ldloc.3
0x16bb09  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bb0e  ldarg.1
0x16bb0f  sub
0x16bb10  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16bb15  call     string [mscorlib]System.String::Concat(string, string)
0x16bb1a  stloc.2
0x16bb1b  ldloc.2
0x16bb1c  callvirt instance string [mscorlib]System.String::Trim()
0x16bb21  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16bb26  brfalse  loc_16BC3B
0x16bb2b  ldarg.s  4
0x16bb2d  ldind.ref
0x16bb2e  ldloc.2
0x16bb2f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x16bb34  ldsfld   string [mscorlib]System.String::Empty
0x16bb39  stloc.2
0x16bb3a  br       loc_16BC3B
0x16bb3f  ldloc.2
0x16bb40  ldarg.2
0x16bb41  ldarg.1
0x16bb42  ldloc.3
0x16bb43  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bb48  ldarg.1
0x16bb49  sub
0x16bb4a  ldloc.3
0x16bb4b  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x16bb50  add
0x16bb51  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16bb56  call     string [mscorlib]System.String::Concat(string, string)
0x16bb5b  stloc.2
0x16bb5c  br       loc_16BC3B
0x16bb61  ldloc.s  7
0x16bb63  brfalse.s loc_16BB94
0x16bb65  ldloc.s  7
0x16bb67  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16bb6c  brfalse.s loc_16BB94
0x16bb6e  ldloc.1
0x16bb6f  ldc.i4.1
0x16bb70  add
0x16bb71  stloc.1
0x16bb72  ldloc.2
0x16bb73  ldarg.2
0x16bb74  ldarg.1
0x16bb75  ldloc.3
0x16bb76  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bb7b  ldarg.1
0x16bb7c  sub
0x16bb7d  ldloc.3
0x16bb7e  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x16bb83  add
0x16bb84  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16bb89  call     string [mscorlib]System.String::Concat(string, string)
0x16bb8e  stloc.2
0x16bb8f  br       loc_16BC3B
0x16bb94  ldloc.s  8
0x16bb96  brfalse.s loc_16BBC4
0x16bb98  ldloc.s  8
0x16bb9a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16bb9f  brfalse.s loc_16BBC4
0x16bba1  ldloc.1
0x16bba2  ldc.i4.1
0x16bba3  sub
0x16bba4  stloc.1
0x16bba5  ldloc.2
0x16bba6  ldarg.2
0x16bba7  ldarg.1
0x16bba8  ldloc.3
0x16bba9  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bbae  ldarg.1
0x16bbaf  sub
0x16bbb0  ldloc.3
0x16bbb1  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x16bbb6  add
0x16bbb7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16bbbc  call     string [mscorlib]System.String::Concat(string, string)
0x16bbc1  stloc.2
0x16bbc2  br.s     loc_16BC3B
0x16bbc4  ldloc.s  6
0x16bbc6  brfalse.s loc_16BC1E
0x16bbc8  ldloc.s  6
0x16bbca  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16bbcf  brfalse.s loc_16BC1E
0x16bbd1  ldc.i4.1
0x16bbd2  ldloc.0
0x16bbd3  bne.un.s loc_16BBFF
0x16bbd5  ldloc.1
0x16bbd6  brtrue.s loc_16BBFF
0x16bbd8  ldloc.2
0x16bbd9  ldarg.2
0x16bbda  ldarg.1
0x16bbdb  ldloc.3
0x16bbdc  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bbe1  ldarg.1
0x16bbe2  sub
0x16bbe3  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16bbe8  call     string [mscorlib]System.String::Concat(string, string)
0x16bbed  stloc.2
0x16bbee  ldarg.s  4
0x16bbf0  ldind.ref
0x16bbf1  ldloc.2
0x16bbf2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x16bbf7  ldsfld   string [mscorlib]System.String::Empty
0x16bbfc  stloc.2
0x16bbfd  br.s     loc_16BC3B
0x16bbff  ldloc.2
0x16bc00  ldarg.2
0x16bc01  ldarg.1
0x16bc02  ldloc.3
0x16bc03  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bc08  ldarg.1
0x16bc09  sub
0x16bc0a  ldloc.3
0x16bc0b  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x16bc10  add
0x16bc11  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16bc16  call     string [mscorlib]System.String::Concat(string, string)
0x16bc1b  stloc.2
0x16bc1c  br.s     loc_16BC3B
0x16bc1e  ldloc.2
0x16bc1f  ldarg.2
0x16bc20  ldarg.1
0x16bc21  ldloc.3
0x16bc22  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bc27  ldarg.1
0x16bc28  sub
0x16bc29  ldloc.3
0x16bc2a  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x16bc2f  add
0x16bc30  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16bc35  call     string [mscorlib]System.String::Concat(string, string)
0x16bc3a  stloc.2
0x16bc3b  ldloc.3
0x16bc3c  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x16bc41  ldloc.3
0x16bc42  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x16bc47  add
0x16bc48  starg.s  1
0x16bc4a  ldc.i4.0
0x16bc4b  ldloc.0
0x16bc4c  bge.s    loc_16BC5A
0x16bc4e  ldarg.1
0x16bc4f  ldarg.2
0x16bc50  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16bc55  blt      loc_16BA47
0x16bc5a  ldloc.0
0x16bc5b  ldc.i4.0
0x16bc5c  ble.s    loc_16BCAF
0x16bc5e  ldarg.0
0x16bc5f  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.RdlExpressions.ExpressionParser::m_errorContext
0x16bc64  ldc.i4.s 0x4E
0x16bc66  ldc.i4.0
0x16bc67  ldarg.0
0x16bc68  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16bc6d  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x16bc72  ldarg.0
0x16bc73  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16bc78  call     instance string ExpressionContext::get_ObjectName()
0x16bc7d  ldarg.0
0x16bc7e  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x16bc83  call     instance string ExpressionContext::get_PropertyName()
0x16bc88  call     T0x2B000001
0x16bc8d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x16bc92  pop
0x16bc93  ldloc.2
0x16bc94  callvirt instance string [mscorlib]System.String::Trim()
0x16bc99  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16bc9e  brfalse.s loc_16BCAF
0x16bca0  ldarg.s  4
0x16bca2  ldind.ref
0x16bca3  ldloc.2
0x16bca4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x16bca9  ldsfld   string [mscorlib]System.String::Empty
0x16bcae  stloc.2
0x16bcaf  ldarg.3
0x16bcb0  ldarg.1
0x16bcb1  stind.i4
0x16bcb2  ret
```
