# Microsoft.ReportingServices.ReportProcessing.VBExpressionParser::GetArguments

- ea: `0x1cff20`
- end: `0x1d011b`
- name: `Microsoft.ReportingServices.ReportProcessing.VBExpressionParser::GetArguments`
- size: `507`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ced90`
- `0x1cf1d0`
- `0x1cf500`
- `0x1cf8c0`

## callees

- `0x1767c0`
- `0x1cff20`
- `0x262870`
- `0x262880`
- `0x262890`

## string_xrefs

- `0x1cff6c`: `${openParen}`
- `0x1cff85`: `${comma}`

## pseudocode

```c

```

## disassembly

```asm
0x1cff20  ldc.i4.1
0x1cff21  stloc.0
0x1cff22  ldarg.s  4
0x1cff24  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1cff29  stind.ref
0x1cff2a  ldsfld   string [mscorlib]System.String::Empty
0x1cff2f  stloc.1
0x1cff30  br       loc_1D00B2
0x1cff35  ldarg.0
0x1cff36  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.ReportProcessing.VBExpressionParser::m_regexes
0x1cff3b  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::Arguments
0x1cff40  ldarg.2
0x1cff41  ldarg.1
0x1cff42  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, int32)
0x1cff47  stloc.2
0x1cff48  ldloc.2
0x1cff49  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x1cff4e  brtrue.s loc_1CFF6B
0x1cff50  ldloc.1
0x1cff51  ldarg.2
0x1cff52  ldarg.1
0x1cff53  callvirt instance string [mscorlib]System.String::Substring(int32)
0x1cff58  call     string [mscorlib]System.String::Concat(string, string)
0x1cff5d  stloc.1
0x1cff5e  ldarg.2
0x1cff5f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cff64  starg.s  1
0x1cff66  br       loc_1D00B2
0x1cff6b  ldloc.2
0x1cff6c  ldstr    aOpenparen// "${openParen}"
0x1cff71  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x1cff76  stloc.3
0x1cff77  ldloc.2
0x1cff78  ldstr    aCloseparen// "${closeParen}"
0x1cff7d  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x1cff82  stloc.s  4
0x1cff84  ldloc.2
0x1cff85  ldstr    aComma// "${comma}"
0x1cff8a  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x1cff8f  stloc.s  5
0x1cff91  ldloc.3
0x1cff92  brfalse.s loc_1CFFC2
0x1cff94  ldloc.3
0x1cff95  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cff9a  brfalse.s loc_1CFFC2
0x1cff9c  ldloc.0
0x1cff9d  ldc.i4.1
0x1cff9e  add
0x1cff9f  stloc.0
0x1cffa0  ldloc.1
0x1cffa1  ldarg.2
0x1cffa2  ldarg.1
0x1cffa3  ldloc.2
0x1cffa4  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x1cffa9  ldarg.1
0x1cffaa  sub
0x1cffab  ldloc.2
0x1cffac  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x1cffb1  add
0x1cffb2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1cffb7  call     string [mscorlib]System.String::Concat(string, string)
0x1cffbc  stloc.1
0x1cffbd  br       loc_1D00A3
0x1cffc2  ldloc.s  4
0x1cffc4  brfalse.s loc_1D002F
0x1cffc6  ldloc.s  4
0x1cffc8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cffcd  brfalse.s loc_1D002F
0x1cffcf  ldloc.0
0x1cffd0  ldc.i4.1
0x1cffd1  sub
0x1cffd2  stloc.0
0x1cffd3  ldloc.0
0x1cffd4  brtrue.s loc_1D0010
0x1cffd6  ldloc.1
0x1cffd7  ldarg.2
0x1cffd8  ldarg.1
0x1cffd9  ldloc.2
0x1cffda  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x1cffdf  ldarg.1
0x1cffe0  sub
0x1cffe1  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1cffe6  call     string [mscorlib]System.String::Concat(string, string)
0x1cffeb  stloc.1
0x1cffec  ldloc.1
0x1cffed  callvirt instance string [mscorlib]System.String::Trim()
0x1cfff2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cfff7  brfalse  loc_1D00A3
0x1cfffc  ldarg.s  4
0x1cfffe  ldind.ref
0x1cffff  ldloc.1
0x1d0000  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1d0005  ldsfld   string [mscorlib]System.String::Empty
0x1d000a  stloc.1
0x1d000b  br       loc_1D00A3
0x1d0010  ldloc.1
0x1d0011  ldarg.2
0x1d0012  ldarg.1
0x1d0013  ldloc.2
0x1d0014  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x1d0019  ldarg.1
0x1d001a  sub
0x1d001b  ldloc.2
0x1d001c  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x1d0021  add
0x1d0022  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1d0027  call     string [mscorlib]System.String::Concat(string, string)
0x1d002c  stloc.1
0x1d002d  br.s     loc_1D00A3
0x1d002f  ldloc.s  5
0x1d0031  brfalse.s loc_1D0086
0x1d0033  ldloc.s  5
0x1d0035  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1d003a  brfalse.s loc_1D0086
0x1d003c  ldc.i4.1
0x1d003d  ldloc.0
0x1d003e  bne.un.s loc_1D0067
0x1d0040  ldloc.1
0x1d0041  ldarg.2
0x1d0042  ldarg.1
0x1d0043  ldloc.2
0x1d0044  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x1d0049  ldarg.1
0x1d004a  sub
0x1d004b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1d0050  call     string [mscorlib]System.String::Concat(string, string)
0x1d0055  stloc.1
0x1d0056  ldarg.s  4
0x1d0058  ldind.ref
0x1d0059  ldloc.1
0x1d005a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1d005f  ldsfld   string [mscorlib]System.String::Empty
0x1d0064  stloc.1
0x1d0065  br.s     loc_1D00A3
0x1d0067  ldloc.1
0x1d0068  ldarg.2
0x1d0069  ldarg.1
0x1d006a  ldloc.2
0x1d006b  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x1d0070  ldarg.1
0x1d0071  sub
0x1d0072  ldloc.2
0x1d0073  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x1d0078  add
0x1d0079  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1d007e  call     string [mscorlib]System.String::Concat(string, string)
0x1d0083  stloc.1
0x1d0084  br.s     loc_1D00A3
0x1d0086  ldloc.1
0x1d0087  ldarg.2
0x1d0088  ldarg.1
0x1d0089  ldloc.2
0x1d008a  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x1d008f  ldarg.1
0x1d0090  sub
0x1d0091  ldloc.2
0x1d0092  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x1d0097  add
0x1d0098  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1d009d  call     string [mscorlib]System.String::Concat(string, string)
0x1d00a2  stloc.1
0x1d00a3  ldloc.2
0x1d00a4  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x1d00a9  ldloc.2
0x1d00aa  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x1d00af  add
0x1d00b0  starg.s  1
0x1d00b2  ldc.i4.0
0x1d00b3  ldloc.0
0x1d00b4  bge.s    loc_1D00C2
0x1d00b6  ldarg.1
0x1d00b7  ldarg.2
0x1d00b8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1d00bd  blt      loc_1CFF35
0x1d00c2  ldloc.0
0x1d00c3  ldc.i4.0
0x1d00c4  ble.s    loc_1D0117
0x1d00c6  ldarg.0
0x1d00c7  ldfld    class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.ReportProcessing.ExpressionParser::m_errorContext
0x1d00cc  ldc.i4.s 0x4E
0x1d00ce  ldc.i4.0
0x1d00cf  ldarg.0
0x1d00d0  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.ReportProcessing.VBExpressionParser::m_context
0x1d00d5  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType ExpressionContext::get_ObjectType()
0x1d00da  ldarg.0
0x1d00db  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.ReportProcessing.VBExpressionParser::m_context
0x1d00e0  call     instance string ExpressionContext::get_ObjectName()
0x1d00e5  ldarg.0
0x1d00e6  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.ReportProcessing.VBExpressionParser::m_context
0x1d00eb  call     instance string ExpressionContext::get_PropertyName()
0x1d00f0  call     T0x2B000001
0x1d00f5  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1d00fa  pop
0x1d00fb  ldloc.1
0x1d00fc  callvirt instance string [mscorlib]System.String::Trim()
0x1d0101  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1d0106  brfalse.s loc_1D0117
0x1d0108  ldarg.s  4
0x1d010a  ldind.ref
0x1d010b  ldloc.1
0x1d010c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1d0111  ldsfld   string [mscorlib]System.String::Empty
0x1d0116  stloc.1
0x1d0117  ldarg.3
0x1d0118  ldarg.1
0x1d0119  stind.i4
0x1d011a  ret
```
