# <GetTokenAsync>d__174::MoveNext

- ea: `0x11d780`
- end: `0x11e571`
- name: `<GetTokenAsync>d__174::MoveNext`
- size: `3569`
- prototype: ``
- caller_count: `0`
- callee_count: `47`
- tags: `registry_config, broker_com_uri`

## callees

- `0xef40`
- `0x15d80`
- `0x15d90`
- `0x15dc0`
- `0x15e00`
- `0x5c5f0`
- `0x5c650`
- `0x5e6d0`
- `0x5e730`
- `0x5ea00`
- `0x5ea70`
- `0x5eb10`
- `0x5eb80`
- `0x5f0b0`
- `0x5f100`
- `0x5f170`
- `0x5f480`
- `0x60080`
- `0x609a0`
- `0x60b20`
- `0x60de0`
- `0x60df0`
- `0x60ef0`
- `0x60f70`
- `0x61690`
- `0x616d0`
- `0x61710`
- `0x61750`
- `0x61790`
- `0x617d0`
- `0x61810`
- `0x61850`
- `0x61890`
- `0x618d0`
- `0x61910`
- `0x61990`
- `0x619d0`
- `0x61a10`
- `0x61a50`
- `0x61a90`
- `0x61ad0`
- `0x61b10`
- `0x61b50`
- `0x61b90`
- `0x61d30`
- `0x61d70`
- `0x11d780`

## string_xrefs

- `0x11da34`: `Xml_ExpectingWhiteSpace`
- `0x11e534`: `Xml_IncompleteDtdContent`

## pseudocode

```c

```

## disassembly

```asm
0x11d780  ldarg.0
0x11d781  ldfld    int32 <GetTokenAsync>d__174::<>1__state
0x11d786  stloc.0
0x11d787  ldarg.0
0x11d788  ldfld    class System.Xml.DtdParser <GetTokenAsync>d__174::<>4__this
0x11d78d  stloc.1
0x11d78e  ldloc.0
0x11d78f  switch   loc_11D9E9, loc_11DB32, loc_11DBA4, loc_11DC16, loc_11DC88, loc_11DCFA, loc_11DD78, loc_11DDEA, loc_11DE5C, loc_11DEFF, loc_11DF72, loc_11E009, loc_11E088, loc_11E0FB, loc_11E16E, loc_11E1E1, loc_11E254, loc_11E2C7, loc_11E33A, loc_11E3AD, loc_11E42C, loc_11E4E0
0x11d7ec  ldloc.1
0x11d7ed  ldc.i4.0
0x11d7ee  stfld    bool System.Xml.DtdParser::whitespaceSeen
0x11d7f3  ldloc.1
0x11d7f4  ldfld    char[] System.Xml.DtdParser::chars
0x11d7f9  ldloc.1
0x11d7fa  ldfld    int32 System.Xml.DtdParser::curPos
0x11d7ff  ldelem.u2
0x11d800  stloc.3
0x11d801  ldloc.3
0x11d802  ldc.i4.s 0xD
0x11d804  bgt.un.s loc_11D82B
0x11d806  ldloc.3
0x11d807  brfalse.s loc_11D840
0x11d809  ldloc.3
0x11d80a  ldc.i4.s 9
0x11d80c  sub
0x11d80d  switch   loc_11D93B, loc_11D86E, loc_11DA13, loc_11DA13, loc_11D899
0x11d826  br       loc_11DA13
0x11d82b  ldloc.3
0x11d82c  ldc.i4.s 0x20
0x11d82e  beq      loc_11D93B
0x11d833  ldloc.3
0x11d834  ldc.i4.s 0x25
0x11d836  beq      loc_11D955
0x11d83b  br       loc_11DA13
0x11d840  ldloc.1
0x11d841  ldfld    int32 System.Xml.DtdParser::curPos
0x11d846  ldloc.1
0x11d847  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11d84c  beq      loc_11E486
0x11d851  ldloc.1
0x11d852  ldloc.1
0x11d853  ldfld    char[] System.Xml.DtdParser::chars
0x11d858  ldloc.1
0x11d859  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11d85e  ldloc.1
0x11d85f  ldfld    int32 System.Xml.DtdParser::curPos
0x11d864  call     instance void System.Xml.DtdParser::ThrowInvalidChar(char[] data, int32 length, int32 invCharPos)
0x11d869  br       loc_11E486
0x11d86e  ldloc.1
0x11d86f  ldc.i4.1
0x11d870  stfld    bool System.Xml.DtdParser::whitespaceSeen
0x11d875  ldloc.1
0x11d876  ldloc.1
0x11d877  ldfld    int32 System.Xml.DtdParser::curPos
0x11d87c  ldc.i4.1
0x11d87d  add
0x11d87e  stfld    int32 System.Xml.DtdParser::curPos
0x11d883  ldloc.1
0x11d884  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x11d889  ldloc.1
0x11d88a  ldfld    int32 System.Xml.DtdParser::curPos
0x11d88f  callvirt instance void System.Xml.IDtdParserAdapter::OnNewLine(int32 pos)
0x11d894  br       loc_11D7F3
0x11d899  ldloc.1
0x11d89a  ldc.i4.1
0x11d89b  stfld    bool System.Xml.DtdParser::whitespaceSeen
0x11d8a0  ldloc.1
0x11d8a1  ldfld    char[] System.Xml.DtdParser::chars
0x11d8a6  ldloc.1
0x11d8a7  ldfld    int32 System.Xml.DtdParser::curPos
0x11d8ac  ldc.i4.1
0x11d8ad  add
0x11d8ae  ldelem.u2
0x11d8af  ldc.i4.s 0xA
0x11d8b1  bne.un.s loc_11D8E8
0x11d8b3  ldloc.1
0x11d8b4  call     instance bool System.Xml.DtdParser::get_Normalize()
0x11d8b9  brfalse.s loc_11D8D8
0x11d8bb  ldloc.1
0x11d8bc  call     instance void System.Xml.DtdParser::SaveParsingBuffer()
0x11d8c1  ldloc.1
0x11d8c2  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x11d8c7  dup
0x11d8c8  callvirt instance int32 System.Xml.IDtdParserAdapter::get_CurrentPosition()
0x11d8cd  stloc.s  4
0x11d8cf  ldloc.s  4
0x11d8d1  ldc.i4.1
0x11d8d2  add
0x11d8d3  callvirt instance void System.Xml.IDtdParserAdapter::set_CurrentPosition(int32 value)
0x11d8d8  ldloc.1
0x11d8d9  ldloc.1
0x11d8da  ldfld    int32 System.Xml.DtdParser::curPos
0x11d8df  ldc.i4.2
0x11d8e0  add
0x11d8e1  stfld    int32 System.Xml.DtdParser::curPos
0x11d8e6  br.s     loc_11D925
0x11d8e8  ldloc.1
0x11d8e9  ldfld    int32 System.Xml.DtdParser::curPos
0x11d8ee  ldc.i4.1
0x11d8ef  add
0x11d8f0  ldloc.1
0x11d8f1  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11d8f6  blt.s    loc_11D908
0x11d8f8  ldloc.1
0x11d8f9  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x11d8fe  callvirt instance bool System.Xml.IDtdParserAdapter::get_IsEof()
0x11d903  brfalse  loc_11E486
0x11d908  ldloc.1
0x11d909  ldfld    char[] System.Xml.DtdParser::chars
0x11d90e  ldloc.1
0x11d90f  ldfld    int32 System.Xml.DtdParser::curPos
0x11d914  ldc.i4.s 0xA
0x11d916  stelem.i2
0x11d917  ldloc.1
0x11d918  ldloc.1
0x11d919  ldfld    int32 System.Xml.DtdParser::curPos
0x11d91e  ldc.i4.1
0x11d91f  add
0x11d920  stfld    int32 System.Xml.DtdParser::curPos
0x11d925  ldloc.1
0x11d926  ldfld    class System.Xml.IDtdParserAdapter System.Xml.DtdParser::readerAdapter
0x11d92b  ldloc.1
0x11d92c  ldfld    int32 System.Xml.DtdParser::curPos
0x11d931  callvirt instance void System.Xml.IDtdParserAdapter::OnNewLine(int32 pos)
0x11d936  br       loc_11D7F3
0x11d93b  ldloc.1
0x11d93c  ldc.i4.1
0x11d93d  stfld    bool System.Xml.DtdParser::whitespaceSeen
0x11d942  ldloc.1
0x11d943  ldloc.1
0x11d944  ldfld    int32 System.Xml.DtdParser::curPos
0x11d949  ldc.i4.1
0x11d94a  add
0x11d94b  stfld    int32 System.Xml.DtdParser::curPos
0x11d950  br       loc_11D7F3
0x11d955  ldloc.1
0x11d956  ldfld    int32 System.Xml.DtdParser::charsUsed
0x11d95b  ldloc.1
0x11d95c  ldfld    int32 System.Xml.DtdParser::curPos
0x11d961  sub
0x11d962  ldc.i4.2
0x11d963  blt      loc_11E486
0x11d968  ldloc.1
0x11d969  ldflda   valuetype System.Xml.XmlCharType System.Xml.DtdParser::xmlCharType
0x11d96e  ldloc.1
0x11d96f  ldfld    char[] System.Xml.DtdParser::chars
0x11d974  ldloc.1
0x11d975  ldfld    int32 System.Xml.DtdParser::curPos
0x11d97a  ldc.i4.1
0x11d97b  add
0x11d97c  ldelem.u2
0x11d97d  call     instance bool System.Xml.XmlCharType::IsWhiteSpace(char ch)
0x11d982  brtrue   loc_11DA13
0x11d987  ldloc.1
0x11d988  call     instance bool System.Xml.DtdParser::get_IgnoreEntityReferences()
0x11d98d  brfalse.s loc_11D9A2
0x11d98f  ldloc.1
0x11d990  ldloc.1
0x11d991  ldfld    int32 System.Xml.DtdParser::curPos
0x11d996  ldc.i4.1
0x11d997  add
0x11d998  stfld    int32 System.Xml.DtdParser::curPos
0x11d99d  br       loc_11D7F3
0x11d9a2  ldloc.1
0x11d9a3  ldc.i4.1
0x11d9a4  ldc.i4.0
0x11d9a5  ldc.i4.0
0x11d9a6  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> System.Xml.DtdParser::HandleEntityReferenceAsync(bool paramEntity, bool inLiteral, bool inAttribute)
0x11d9ab  ldc.i4.0
0x11d9ac  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x11d9b1  stloc.s  6
0x11d9b3  ldloca.s 6
0x11d9b5  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x11d9ba  stloc.s  5
0x11d9bc  ldloca.s 5
0x11d9be  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x11d9c3  brtrue.s loc_11DA06
0x11d9c5  ldarg.0
0x11d9c6  ldc.i4.0
0x11d9c7  dup
0x11d9c8  stloc.0
0x11d9c9  stfld    int32 <GetTokenAsync>d__174::<>1__state
0x11d9ce  ldarg.0
0x11d9cf  ldloc.s  5
0x11d9d1  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <GetTokenAsync>d__174::<>u__1
0x11d9d6  ldarg.0
0x11d9d7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype Token> <GetTokenAsync>d__174::<>t__builder
0x11d9dc  ldloca.s 5
0x11d9de  ldarg.0
0x11d9df  call     T0x2B0002BB
0x11d9e4  leave    loc_11E570
0x11d9e9  ldarg.0
0x11d9ea  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <GetTokenAsync>d__174::<>u__1
0x11d9ef  stloc.s  5
0x11d9f1  ldarg.0
0x11d9f2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <GetTokenAsync>d__174::<>u__1
0x11d9f7  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x11d9fd  ldarg.0
0x11d9fe  ldc.i4.m1
0x11d9ff  dup
0x11da00  stloc.0
0x11da01  stfld    int32 <GetTokenAsync>d__174::<>1__state
0x11da06  ldloca.s 5
0x11da08  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x11da0d  pop
0x11da0e  br       loc_11D7F3
0x11da13  ldarg.0
0x11da14  ldfld    bool <GetTokenAsync>d__174::needWhiteSpace
0x11da19  brfalse.s loc_11DA4A
0x11da1b  ldloc.1
0x11da1c  ldfld    bool System.Xml.DtdParser::whitespaceSeen
0x11da21  brtrue.s loc_11DA4A
0x11da23  ldloc.1
0x11da24  ldfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11da29  ldc.i4.s 0x20
0x11da2b  beq.s    loc_11DA4A
0x11da2d  ldloc.1
0x11da2e  ldloc.1
0x11da2f  ldfld    int32 System.Xml.DtdParser::curPos
0x11da34  ldstr    aXmlExpectingwh// "Xml_ExpectingWhiteSpace"
0x11da39  ldloc.1
0x11da3a  ldloc.1
0x11da3b  ldfld    int32 System.Xml.DtdParser::curPos
0x11da40  call     instance string System.Xml.DtdParser::ParseUnexpectedToken(int32 startPos)
0x11da45  call     instance void System.Xml.DtdParser::Throw(int32 curPos, string res, string arg)
0x11da4a  ldloc.1
0x11da4b  ldloc.1
0x11da4c  ldfld    int32 System.Xml.DtdParser::curPos
0x11da51  stfld    int32 System.Xml.DtdParser::tokenStartPos
0x11da56  ldloc.1
0x11da57  ldfld    valuetype ScanningFunction System.Xml.DtdParser::scanningFunction
0x11da5c  stloc.s  7
0x11da5e  ldloc.s  7
0x11da60  switch   loc_11DC44, loc_11DAEE, loc_11DB60, loc_11DBD2, loc_11DCB6, loc_11DD28, loc_11DD34, loc_11DDA6, loc_11DE18, loc_11DE8A, loc_11DE96, loc_11DEA2, loc_11DEAE, loc_11DEBA, loc_11DF2D, loc_11DFA0, loc_11DFAC, loc_11DFB8, loc_11DFC4, loc_11E037, loc_11E20F, loc_11E282, loc_11E2F5, loc_11E043, loc_11E368, loc_11E3DB, loc_11E3E7, loc_11E47E, loc_11E0B6, loc_11E129, loc_11E19C, loc_11E45A, loc_11E466
0x11dae9  br       loc_11E47E
0x11daee  ldloc.1
0x11daef  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::ScanNameExpectedAsync()
0x11daf4  ldc.i4.0
0x11daf5  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11dafa  stloc.s  0xA
0x11dafc  ldloca.s 0xA
0x11dafe  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11db03  stloc.s  9
0x11db05  ldloca.s 9
0x11db07  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11db0c  brtrue.s loc_11DB4F
0x11db0e  ldarg.0
0x11db0f  ldc.i4.1
0x11db10  dup
0x11db11  stloc.0
0x11db12  stfld    int32 <GetTokenAsync>d__174::<>1__state
0x11db17  ldarg.0
0x11db18  ldloc.s  9
0x11db1a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <GetTokenAsync>d__174::<>u__2
0x11db1f  ldarg.0
0x11db20  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype Token> <GetTokenAsync>d__174::<>t__builder
0x11db25  ldloca.s 9
0x11db27  ldarg.0
0x11db28  call     T0x2B0002BC
0x11db2d  leave    loc_11E570
0x11db32  ldarg.0
0x11db33  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <GetTokenAsync>d__174::<>u__2
0x11db38  stloc.s  9
0x11db3a  ldarg.0
0x11db3b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <GetTokenAsync>d__174::<>u__2
0x11db40  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>
0x11db46  ldarg.0
0x11db47  ldc.i4.m1
0x11db48  dup
0x11db49  stloc.0
0x11db4a  stfld    int32 <GetTokenAsync>d__174::<>1__state
0x11db4f  ldloca.s 9
0x11db51  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::GetResult()
0x11db56  stloc.s  8
0x11db58  ldloc.s  8
0x11db5a  stloc.2
0x11db5b  leave    loc_11E55C
0x11db60  ldloc.1
0x11db61  call     instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token> System.Xml.DtdParser::ScanQNameExpectedAsync()
0x11db66  ldc.i4.0
0x11db67  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<valuetype Token>::ConfigureAwait(!!T0)
0x11db6c  stloc.s  0xA
0x11db6e  ldloca.s 0xA
0x11db70  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<valuetype Token>::GetAwaiter()
0x11db75  stloc.s  0xC
0x11db77  ldloca.s 0xC
0x11db79  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token>::get_IsCompleted()
0x11db7e  brtrue.s loc_11DBC1
0x11db80  ldarg.0
0x11db81  ldc.i4.2
0x11db82  dup
0x11db83  stloc.0
0x11db84  stfld    int32 <GetTokenAsync>d__174::<>1__state
0x11db89  ldarg.0
0x11db8a  ldloc.s  0xC
0x11db8c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<valuetype Token> <GetTokenAsync>d__174::<>u__2
0x11db91  ldarg.0
0x11db92  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<valuetype Token> <GetTokenAsync>d__174::<>t__builder
0x11db97  ldloca.s 0xC
0x11db99  ldarg.0
  ... truncated ...
```
