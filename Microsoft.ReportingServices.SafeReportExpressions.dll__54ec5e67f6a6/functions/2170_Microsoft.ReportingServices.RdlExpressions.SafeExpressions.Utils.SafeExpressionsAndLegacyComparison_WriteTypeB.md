# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteTypeBasedDifferences

- ea: `0x2170`
- end: `0x26a7`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteTypeBasedDifferences`
- size: `1335`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e10`

## callees

- `0x2170`
- `0x2710`
- `0x2730`
- `0x27c0`

## pseudocode

```c

```

## disassembly

```asm
0x2170  ldarg.3
0x2171  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2176  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x217b  stloc.0
0x217c  ldarg.2
0x217d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2182  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x2187  stloc.1
0x2188  ldloc.0
0x2189  ldloc.1
0x218a  beq.s    loc_218D
0x218c  ret
0x218d  ldloc.0
0x218e  ldc.i4.1
0x218f  sub
0x2190  switch   loc_2541, loc_26A6, loc_26A6, loc_26A6, loc_2230, loc_2274, loc_22B8, loc_22FC, loc_2340, loc_2384, loc_23C8, loc_240B, loc_2450, loc_2495, loc_24DA, loc_21DE, loc_26A6, loc_2523
0x21dd  ret
0x21de  ldarg.0
0x21df  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x21e4  unbox.any [mscorlib]System.DateTime
0x21e9  ldarg.0
0x21ea  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x21ef  unbox.any [mscorlib]System.DateTime
0x21f4  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x21f9  stloc.3
0x21fa  ldarg.1
0x21fb  ldstr    aDatetimeresult// "DateTimeResultDiffMs"
0x2200  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WritePropertyName(string)
0x2205  ldarg.1
0x2206  ldloca.s 3
0x2208  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x220d  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonWriter::WriteValue(float64)
0x2212  ldarg.0
0x2213  ldarg.1
0x2214  ldarg.0
0x2215  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x221a  callvirt instance string [mscorlib]System.Object::ToString()
0x221f  ldarg.0
0x2220  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2225  callvirt instance string [mscorlib]System.Object::ToString()
0x222a  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x222f  ret
0x2230  ldarg.0
0x2231  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2236  unbox.any [mscorlib]System.SByte
0x223b  ldarg.0
0x223c  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x2241  unbox.any [mscorlib]System.SByte
0x2246  sub
0x2247  conv.i8
0x2248  stloc.2
0x2249  ldarg.0
0x224a  ldarg.1
0x224b  ldloc.2
0x224c  box      [mscorlib]System.Int64
0x2251  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x2256  ldarg.0
0x2257  ldarg.1
0x2258  ldarg.0
0x2259  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x225e  callvirt instance string [mscorlib]System.Object::ToString()
0x2263  ldarg.0
0x2264  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2269  callvirt instance string [mscorlib]System.Object::ToString()
0x226e  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x2273  ret
0x2274  ldarg.0
0x2275  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x227a  unbox.any [mscorlib]System.Byte
0x227f  ldarg.0
0x2280  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x2285  unbox.any [mscorlib]System.Byte
0x228a  sub
0x228b  conv.i8
0x228c  stloc.2
0x228d  ldarg.0
0x228e  ldarg.1
0x228f  ldloc.2
0x2290  box      [mscorlib]System.Int64
0x2295  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x229a  ldarg.0
0x229b  ldarg.1
0x229c  ldarg.0
0x229d  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x22a2  callvirt instance string [mscorlib]System.Object::ToString()
0x22a7  ldarg.0
0x22a8  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x22ad  callvirt instance string [mscorlib]System.Object::ToString()
0x22b2  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x22b7  ret
0x22b8  ldarg.0
0x22b9  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x22be  unbox.any [mscorlib]System.Int16
0x22c3  ldarg.0
0x22c4  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x22c9  unbox.any [mscorlib]System.Int16
0x22ce  sub
0x22cf  conv.i8
0x22d0  stloc.2
0x22d1  ldarg.0
0x22d2  ldarg.1
0x22d3  ldloc.2
0x22d4  box      [mscorlib]System.Int64
0x22d9  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x22de  ldarg.0
0x22df  ldarg.1
0x22e0  ldarg.0
0x22e1  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x22e6  callvirt instance string [mscorlib]System.Object::ToString()
0x22eb  ldarg.0
0x22ec  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x22f1  callvirt instance string [mscorlib]System.Object::ToString()
0x22f6  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x22fb  ret
0x22fc  ldarg.0
0x22fd  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2302  unbox.any [mscorlib]System.UInt16
0x2307  ldarg.0
0x2308  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x230d  unbox.any [mscorlib]System.UInt16
0x2312  sub
0x2313  conv.i8
0x2314  stloc.2
0x2315  ldarg.0
0x2316  ldarg.1
0x2317  ldloc.2
0x2318  box      [mscorlib]System.Int64
0x231d  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x2322  ldarg.0
0x2323  ldarg.1
0x2324  ldarg.0
0x2325  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x232a  callvirt instance string [mscorlib]System.Object::ToString()
0x232f  ldarg.0
0x2330  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2335  callvirt instance string [mscorlib]System.Object::ToString()
0x233a  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x233f  ret
0x2340  ldarg.0
0x2341  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2346  unbox.any [mscorlib]System.Int32
0x234b  ldarg.0
0x234c  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x2351  unbox.any [mscorlib]System.Int32
0x2356  sub
0x2357  conv.i8
0x2358  stloc.2
0x2359  ldarg.0
0x235a  ldarg.1
0x235b  ldloc.2
0x235c  box      [mscorlib]System.Int64
0x2361  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x2366  ldarg.0
0x2367  ldarg.1
0x2368  ldarg.0
0x2369  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x236e  callvirt instance string [mscorlib]System.Object::ToString()
0x2373  ldarg.0
0x2374  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2379  callvirt instance string [mscorlib]System.Object::ToString()
0x237e  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x2383  ret
0x2384  ldarg.0
0x2385  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x238a  unbox.any [mscorlib]System.UInt32
0x238f  ldarg.0
0x2390  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x2395  unbox.any [mscorlib]System.UInt32
0x239a  sub
0x239b  conv.u8
0x239c  stloc.2
0x239d  ldarg.0
0x239e  ldarg.1
0x239f  ldloc.2
0x23a0  box      [mscorlib]System.Int64
0x23a5  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x23aa  ldarg.0
0x23ab  ldarg.1
0x23ac  ldarg.0
0x23ad  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x23b2  callvirt instance string [mscorlib]System.Object::ToString()
0x23b7  ldarg.0
0x23b8  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x23bd  callvirt instance string [mscorlib]System.Object::ToString()
0x23c2  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x23c7  ret
0x23c8  ldarg.0
0x23c9  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x23ce  unbox.any [mscorlib]System.Int64
0x23d3  ldarg.0
0x23d4  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x23d9  unbox.any [mscorlib]System.Int64
0x23de  sub
0x23df  stloc.2
0x23e0  ldarg.0
0x23e1  ldarg.1
0x23e2  ldloc.2
0x23e3  box      [mscorlib]System.Int64
0x23e8  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x23ed  ldarg.0
0x23ee  ldarg.1
0x23ef  ldarg.0
0x23f0  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x23f5  callvirt instance string [mscorlib]System.Object::ToString()
0x23fa  ldarg.0
0x23fb  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2400  callvirt instance string [mscorlib]System.Object::ToString()
0x2405  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x240a  ret
0x240b  ldarg.0
0x240c  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2411  unbox.any [mscorlib]System.UInt64
0x2416  ldarg.0
0x2417  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x241c  unbox.any [mscorlib]System.UInt64
0x2421  sub
0x2422  stloc.s  4
0x2424  ldarg.0
0x2425  ldarg.1
0x2426  ldloc.s  4
0x2428  box      [mscorlib]System.UInt64
0x242d  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x2432  ldarg.0
0x2433  ldarg.1
0x2434  ldarg.0
0x2435  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x243a  callvirt instance string [mscorlib]System.Object::ToString()
0x243f  ldarg.0
0x2440  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2445  callvirt instance string [mscorlib]System.Object::ToString()
0x244a  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x244f  ret
0x2450  ldarg.0
0x2451  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2456  unbox.any [mscorlib]System.Single
0x245b  ldarg.0
0x245c  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x2461  unbox.any [mscorlib]System.Single
0x2466  sub
0x2467  stloc.s  5
0x2469  ldarg.0
0x246a  ldarg.1
0x246b  ldloc.s  5
0x246d  box      [mscorlib]System.Single
0x2472  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x2477  ldarg.0
0x2478  ldarg.1
0x2479  ldarg.0
0x247a  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x247f  callvirt instance string [mscorlib]System.Object::ToString()
0x2484  ldarg.0
0x2485  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x248a  callvirt instance string [mscorlib]System.Object::ToString()
0x248f  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x2494  ret
0x2495  ldarg.0
0x2496  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x249b  unbox.any [mscorlib]System.Double
0x24a0  ldarg.0
0x24a1  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x24a6  unbox.any [mscorlib]System.Double
0x24ab  sub
0x24ac  stloc.s  6
0x24ae  ldarg.0
0x24af  ldarg.1
0x24b0  ldloc.s  6
0x24b2  box      [mscorlib]System.Double
0x24b7  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x24bc  ldarg.0
0x24bd  ldarg.1
0x24be  ldarg.0
0x24bf  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x24c4  callvirt instance string [mscorlib]System.Object::ToString()
0x24c9  ldarg.0
0x24ca  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x24cf  callvirt instance string [mscorlib]System.Object::ToString()
0x24d4  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
0x24d9  ret
0x24da  ldarg.0
0x24db  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x24e0  unbox.any [mscorlib]System.Decimal
0x24e5  ldarg.0
0x24e6  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x24eb  unbox.any [mscorlib]System.Decimal
0x24f0  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Subtraction(valuetype [mscorlib]System.Decimal, valuetype [mscorlib]System.Decimal)
0x24f5  stloc.s  7
0x24f7  ldarg.0
0x24f8  ldarg.1
0x24f9  ldloc.s  7
0x24fb  box      [mscorlib]System.Decimal
0x2500  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteNumericResultDiff(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, object diff)
0x2505  ldarg.0
0x2506  ldarg.1
0x2507  ldarg.0
0x2508  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_legacyResult
0x250d  callvirt instance string [mscorlib]System.Object::ToString()
0x2512  ldarg.0
0x2513  ldfld    object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::_safeExprResult
0x2518  callvirt instance string [mscorlib]System.Object::ToString()
0x251d  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchingIndicesForSimpleObjects(class [Newtonsoft.Json]Newtonsoft.Json.JsonWriter jsonWriter, string legacyResult, string safeExprResult)
  ... truncated ...
```
