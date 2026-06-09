# Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::TryVBLex

- ea: `0x167a80`
- end: `0x168007`
- name: `Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::TryVBLex`
- size: `1415`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `service_task, broker_com_uri`

## callers

- `0x1679f0`

## callees

- `0xba260`
- `0xef640`
- `0x117860`
- `0x117870`
- `0x117890`
- `0x1179f0`
- `0x117b10`
- `0x1185d0`
- `0x1185f0`
- `0x118760`
- `0x1187c0`
- `0x1187e0`
- `0x118800`
- `0x118940`
- `0x1189b0`
- `0x153360`
- `0x167a80`
- `0x168090`
- `0x1680a0`
- `0x169100`
- `0x169110`
- `0x169190`
- `0x1691a0`
- `0x1692a0`
- `0x169360`
- `0x169510`
- `0x169660`
- `0x169730`
- `0x169780`
- `0x1697d0`
- `0x1698a0`
- `0x169ea0`
- `0x16a490`
- `0x16aa20`
- `0x16ade0`
- `0x16aed0`
- `0x16bcc0`
- `0x1767c0`
- `0x232c60`
- `0x232c70`
- `0x232c80`
- `0x232ce0`
- `0x23c690`
- `0x23c6a0`

## string_xrefs

- `0x167b49`: `${scopename}`

## pseudocode

```c

```

## disassembly

```asm
0x167a80  ldarg.3
0x167a81  ldc.i4.8
0x167a82  and
0x167a83  brtrue.s loc_167ABA
0x167a85  ldarg.0
0x167a86  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x167a8b  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::FieldOnly
0x167a90  ldarg.1
0x167a91  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x167a96  stloc.s  4
0x167a98  ldloc.s  4
0x167a9a  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x167a9f  brfalse.s loc_167ABA
0x167aa1  ldloc.s  4
0x167aa3  ldstr    aFieldname_0// "${fieldname}"
0x167aa8  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x167aad  stloc.s  5
0x167aaf  ldarg.s  4
0x167ab1  ldloc.s  5
0x167ab3  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::SetAsSimpleFieldReference(string fieldName)
0x167ab8  ldc.i4.1
0x167ab9  ret
0x167aba  ldarg.3
0x167abb  ldc.i4   0x100
0x167ac0  and
0x167ac1  brtrue.s loc_167B09
0x167ac3  ldarg.0
0x167ac4  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x167ac9  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::RewrittenCommandText
0x167ace  ldarg.1
0x167acf  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x167ad4  stloc.s  6
0x167ad6  ldloc.s  6
0x167ad8  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x167add  brfalse.s loc_167B09
0x167adf  ldloc.s  6
0x167ae1  ldstr    aDatasetname_0// "${datasetname}"
0x167ae6  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x167aeb  stloc.s  7
0x167aed  ldarg.s  4
0x167aef  ldloc.s  7
0x167af1  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::AddReferencedDataSet(string dataSetName)
0x167af6  ldarg.s  4
0x167af8  ldc.i4.4
0x167af9  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::set_Type(valuetype Types value)
0x167afe  ldarg.s  4
0x167b00  ldloc.s  7
0x167b02  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::set_StringValue(string value)
0x167b07  ldc.i4.1
0x167b08  ret
0x167b09  ldarg.3
0x167b0a  ldc.i4.8
0x167b0b  and
0x167b0c  brtrue.s loc_167B70
0x167b0e  ldarg.3
0x167b0f  ldc.i4   0x10000
0x167b14  and
0x167b15  brtrue.s loc_167B70
0x167b17  ldarg.0
0x167b18  ldflda   valuetype ExpressionContext Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_context
0x167b1d  call     instance class Microsoft.ReportingServices.ReportPublishing.PublishingVersioning ExpressionContext::get_PublishingVersioning()
0x167b22  ldc.i4.s 0x1E
0x167b24  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.PublishingVersioning::IsRdlFeatureRestricted(valuetype Microsoft.ReportingServices.ReportPublishing.RdlFeatures feature)
0x167b29  brtrue.s loc_167B70
0x167b2b  ldarg.0
0x167b2c  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x167b31  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::ScopedFieldReferenceOnly
0x167b36  ldarg.1
0x167b37  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x167b3c  stloc.s  8
0x167b3e  ldloc.s  8
0x167b40  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x167b45  brfalse.s loc_167B70
0x167b47  ldloc.s  8
0x167b49  ldstr    aScopename// "${scopename}"
0x167b4e  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x167b53  stloc.s  9
0x167b55  ldloc.s  8
0x167b57  ldstr    aFieldname_0// "${fieldname}"
0x167b5c  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x167b61  stloc.s  0xA
0x167b63  ldarg.s  4
0x167b65  ldloc.s  9
0x167b67  ldloc.s  0xA
0x167b69  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::SetAsScopedFieldReference(string scopeName, string fieldName)
0x167b6e  ldc.i4.1
0x167b6f  ret
0x167b70  ldarg.0
0x167b71  ldarga.s 1
0x167b73  ldarg.2
0x167b74  ldarg.3
0x167b75  ldarg.s  4
0x167b77  call     instance void Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::EnforceRestrictions(string& expression, bool isParameter, valuetype GrammarFlags grammarFlags, class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo)
0x167b7c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x167b81  stloc.0
0x167b82  ldc.i4.0
0x167b83  stloc.1
0x167b84  ldc.i4.0
0x167b85  stloc.2
0x167b86  br       loc_167F09
0x167b8b  ldarg.s  5
0x167b8d  brfalse.s loc_167BF9
0x167b8f  ldarg.0
0x167b90  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x167b95  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::RdlFunction
0x167b9a  ldarg.1
0x167b9b  ldloc.1
0x167b9c  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, int32)
0x167ba1  stloc.s  0xC
0x167ba3  ldloc.s  0xC
0x167ba5  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x167baa  brfalse.s loc_167BF6
0x167bac  ldloc.s  0xC
0x167bae  ldstr    aFunctionname// "${functionName}"
0x167bb3  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x167bb8  stloc.s  0xD
0x167bba  ldloc.s  0xD
0x167bbc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x167bc1  brfalse.s loc_167BC5
0x167bc3  ldc.i4.0
0x167bc4  ret
0x167bc5  ldloc.s  0xC
0x167bc7  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x167bcc  stloc.1
0x167bcd  ldarg.0
0x167bce  ldarg.s  4
0x167bd0  ldloc.1
0x167bd1  ldloc.s  0xD
0x167bd3  ldarg.1
0x167bd4  ldarg.3
0x167bd5  ldloca.s 1
0x167bd7  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::ParseRdlFunction(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo expressionInfo, int32 currentPos, string functionName, string expression, valuetype GrammarFlags grammarFlags, [out] int32& newPos)
0x167bdc  brtrue.s loc_167BF2
0x167bde  ldarg.1
0x167bdf  ldloc.1
0x167be0  callvirt instance string [mscorlib]System.String::Substring(int32)
0x167be5  callvirt instance string [mscorlib]System.String::Trim()
0x167bea  callvirt instance int32 [mscorlib]System.String::get_Length()
0x167bef  ldc.i4.0
0x167bf0  ble.s    loc_167BF4
0x167bf2  ldc.i4.0
0x167bf3  ret
0x167bf4  ldc.i4.1
0x167bf5  ret
0x167bf6  ldc.i4.0
0x167bf7  starg.s  5
0x167bf9  ldarg.0
0x167bfa  ldfld    class ReportRegularExpressions Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_regexes
0x167bff  ldfld    class [System]System.Text.RegularExpressions.Regex ReportRegularExpressions::SpecialFunction
0x167c04  ldarg.1
0x167c05  ldloc.1
0x167c06  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, int32)
0x167c0b  stloc.s  0xB
0x167c0d  ldloc.s  0xB
0x167c0f  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x167c14  brtrue.s loc_167C30
0x167c16  ldloc.0
0x167c17  ldarg.1
0x167c18  ldloc.1
0x167c19  callvirt instance string [mscorlib]System.String::Substring(int32)
0x167c1e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x167c23  pop
0x167c24  ldarg.1
0x167c25  callvirt instance int32 [mscorlib]System.String::get_Length()
0x167c2a  stloc.1
0x167c2b  br       loc_167F09
0x167c30  ldloc.0
0x167c31  ldarg.1
0x167c32  ldloc.1
0x167c33  ldloc.s  0xB
0x167c35  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x167c3a  ldloc.1
0x167c3b  sub
0x167c3c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x167c41  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x167c46  pop
0x167c47  ldloc.s  0xB
0x167c49  ldstr    aSfname// "${sfname}"
0x167c4e  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x167c53  stloc.s  0xE
0x167c55  ldloc.s  0xE
0x167c57  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x167c5c  brfalse.s loc_167C81
0x167c5e  ldloc.0
0x167c5f  ldloc.s  0xB
0x167c61  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x167c66  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x167c6b  pop
0x167c6c  ldloc.s  0xB
0x167c6e  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x167c73  ldloc.s  0xB
0x167c75  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x167c7a  add
0x167c7b  stloc.1
0x167c7c  br       loc_167F09
0x167c81  ldloc.0
0x167c82  ldloc.s  0xB
0x167c84  ldstr    aPrefix// "${prefix}"
0x167c89  callvirt instance string [System]System.Text.RegularExpressions.Match::Result(string)
0x167c8e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x167c93  pop
0x167c94  ldloc.s  0xB
0x167c96  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Index()
0x167c9b  ldloc.s  0xB
0x167c9d  callvirt instance int32 [System]System.Text.RegularExpressions.Capture::get_Length()
0x167ca2  add
0x167ca3  stloc.1
0x167ca4  ldc.i4.0
0x167ca5  stloc.s  0x11
0x167ca7  ldarg.0
0x167ca8  ldloc.s  0xE
0x167caa  ldstr    aLookup// "Lookup"
0x167caf  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::AreEqualOrdinalIgnoreCase(string str1, string str2)
0x167cb4  brfalse.s loc_167CDA
0x167cb6  ldc.i4.5
0x167cb7  stloc.s  0x10
0x167cb9  ldarg.0
0x167cba  ldloc.1
0x167cbb  ldloc.s  0xE
0x167cbd  ldarg.1
0x167cbe  ldarg.2
0x167cbf  ldarg.3
0x167cc0  ldc.i4.0
0x167cc1  ldloca.s 1
0x167cc3  ldloca.s 0xF
0x167cc5  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::GetLookup(int32 currentPos, string functionName, string expression, bool isParameter, valuetype GrammarFlags grammarFlags, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.LookupType lookupType, [out] int32& newPos, [out] string& lookupID)
0x167cca  stloc.s  0x12
0x167ccc  ldarg.s  4
0x167cce  ldloc.s  0x12
0x167cd0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::AddLookup(class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo lookup)
0x167cd5  br       loc_167E2C
0x167cda  ldarg.0
0x167cdb  ldloc.s  0xE
0x167cdd  ldstr    aLookupset// "LookupSet"
0x167ce2  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::AreEqualOrdinalIgnoreCase(string str1, string str2)
0x167ce7  brfalse.s loc_167D0D
0x167ce9  ldc.i4.6
0x167cea  stloc.s  0x10
0x167cec  ldarg.0
0x167ced  ldloc.1
0x167cee  ldloc.s  0xE
0x167cf0  ldarg.1
0x167cf1  ldarg.2
0x167cf2  ldarg.3
0x167cf3  ldc.i4.1
0x167cf4  ldloca.s 1
0x167cf6  ldloca.s 0xF
0x167cf8  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::GetLookup(int32 currentPos, string functionName, string expression, bool isParameter, valuetype GrammarFlags grammarFlags, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.LookupType lookupType, [out] int32& newPos, [out] string& lookupID)
0x167cfd  stloc.s  0x13
0x167cff  ldarg.s  4
0x167d01  ldloc.s  0x13
0x167d03  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::AddLookup(class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo lookup)
0x167d08  br       loc_167E2C
0x167d0d  ldarg.0
0x167d0e  ldloc.s  0xE
0x167d10  ldstr    aMultilookup// "MultiLookup"
0x167d15  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::AreEqualOrdinalIgnoreCase(string str1, string str2)
0x167d1a  brfalse.s loc_167D40
0x167d1c  ldc.i4.6
0x167d1d  stloc.s  0x10
0x167d1f  ldarg.0
0x167d20  ldloc.1
0x167d21  ldloc.s  0xE
0x167d23  ldarg.1
0x167d24  ldarg.2
0x167d25  ldarg.3
0x167d26  ldc.i4.2
0x167d27  ldloca.s 1
0x167d29  ldloca.s 0xF
0x167d2b  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::GetLookup(int32 currentPos, string functionName, string expression, bool isParameter, valuetype GrammarFlags grammarFlags, valuetype Microsoft.ReportingServices.ReportIntermediateFormat.LookupType lookupType, [out] int32& newPos, [out] string& lookupID)
0x167d30  stloc.s  0x14
0x167d32  ldarg.s  4
0x167d34  ldloc.s  0x14
0x167d36  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::AddLookup(class Microsoft.ReportingServices.ReportIntermediateFormat.LookupInfo lookup)
0x167d3b  br       loc_167E2C
0x167d40  ldarg.0
0x167d41  call     instance string Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::CreateAggregateID()
0x167d46  stloc.s  0xF
0x167d48  ldarg.0
0x167d49  ldfld    class ParserState Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::m_state
0x167d4e  dup
0x167d4f  callvirt instance int32 ParserState::get_NumberOfAggregates()
0x167d54  stloc.s  0x15
0x167d56  ldloc.s  0x15
0x167d58  ldc.i4.1
0x167d59  add
0x167d5a  callvirt instance void ParserState::set_NumberOfAggregates(int32 value)
0x167d5f  ldc.i4.2
0x167d60  stloc.s  0x10
0x167d62  ldarg.0
0x167d63  ldloc.s  0xE
0x167d65  ldstr    aPrevious_0// "Previous"
0x167d6a  call     instance bool Microsoft.ReportingServices.RdlExpressions.VBExpressionParser::AreEqualOrdinalIgnoreCase(string str1, string str2)
0x167d6f  brfalse.s loc_167D9B
0x167d71  ldarg.0
0x167d72  ldloc.1
0x167d73  ldloc.s  0xE
0x167d75  ldarg.1
0x167d76  ldarg.2
0x167d77  ldarg.3
  ... truncated ...
```
