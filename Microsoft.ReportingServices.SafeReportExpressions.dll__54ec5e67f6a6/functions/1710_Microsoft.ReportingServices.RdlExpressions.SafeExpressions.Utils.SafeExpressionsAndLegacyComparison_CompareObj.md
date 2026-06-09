# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareObjects

- ea: `0x1710`
- end: `0x19b4`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareObjects`
- size: `676`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x16f0`
- `0x19d0`

## callees

- `0x1710`
- `0x19c0`
- `0x1db0`
- `0x1e10`
- `0x2de0`

## pseudocode

```c

```

## disassembly

```asm
0x1710  newobj   instance void <>c__DisplayClass21_0::.ctor()
0x1715  stloc.0
0x1716  ldloc.0
0x1717  ldarg.0
0x1718  stfld    class Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison <>c__DisplayClass21_0::<>4__this
0x171d  ldloc.0
0x171e  ldarg.1
0x171f  stfld    object <>c__DisplayClass21_0::legacyExprResult
0x1724  ldloc.0
0x1725  ldarg.2
0x1726  stfld    object <>c__DisplayClass21_0::safeExprResult
0x172b  ldarg.0
0x172c  ldloc.0
0x172d  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x1732  ldloc.0
0x1733  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x1738  ldloca.s 1
0x173a  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::TryCheckForNullValues(object legacyExprResult, object safeExprResult, [out] bool& result)
0x173f  brfalse.s loc_174C
0x1741  ldloc.1
0x1742  brtrue.s loc_174A
0x1744  ldarg.0
0x1745  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchDetails()
0x174a  ldloc.1
0x174b  ret
0x174c  ldloc.0
0x174d  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x1752  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1757  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x175c  stloc.2
0x175d  ldloc.0
0x175e  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x1763  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1768  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x176d  stloc.3
0x176e  ldloc.2
0x176f  ldloc.3
0x1770  beq.s    loc_177A
0x1772  ldarg.0
0x1773  call     instance void Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::WriteMismatchDetails()
0x1778  ldc.i4.0
0x1779  ret
0x177a  ldloc.0
0x177b  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x1780  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1785  stloc.s  4
0x1787  ldloc.2
0x1788  switch   loc_17DE, loc_17E0, loc_17DE, loc_1881, loc_1894, loc_18A7, loc_18BA, loc_18CD, loc_18E0, loc_18F3, loc_1906, loc_1919, loc_192C, loc_193F, loc_1952, loc_1965, loc_1978, loc_199E, loc_198B
0x17d9  br       loc_199E
0x17de  ldc.i4.1
0x17df  ret
0x17e0  ldloc.s  4
0x17e2  callvirt instance bool [mscorlib]System.Type::get_IsArray()
0x17e7  brfalse.s loc_17FC
0x17e9  ldarg.0
0x17ea  ldloc.0
0x17eb  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__0()
0x17f1  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x17f6  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x17fb  ret
0x17fc  ldloc.s  4
0x17fe  ldtoken  [mscorlib]System.Guid
0x1803  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1808  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x180d  brfalse.s loc_1822
0x180f  ldarg.0
0x1810  ldloc.0
0x1811  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__1()
0x1817  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x181c  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1821  ret
0x1822  ldloc.s  4
0x1824  ldtoken  [mscorlib]System.DateTimeOffset
0x1829  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x182e  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1833  brfalse.s loc_1848
0x1835  ldarg.0
0x1836  ldloc.0
0x1837  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__2()
0x183d  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1842  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1847  ret
0x1848  ldloc.s  4
0x184a  ldtoken  [mscorlib]System.TimeSpan
0x184f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1854  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1859  brfalse.s loc_186E
0x185b  ldarg.0
0x185c  ldloc.0
0x185d  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__3()
0x1863  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1868  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x186d  ret
0x186e  ldarg.0
0x186f  ldloc.0
0x1870  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__4()
0x1876  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x187b  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1880  ret
0x1881  ldarg.0
0x1882  ldloc.0
0x1883  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__5()
0x1889  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x188e  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1893  ret
0x1894  ldarg.0
0x1895  ldloc.0
0x1896  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__6()
0x189c  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x18a1  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x18a6  ret
0x18a7  ldarg.0
0x18a8  ldloc.0
0x18a9  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__7()
0x18af  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x18b4  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x18b9  ret
0x18ba  ldarg.0
0x18bb  ldloc.0
0x18bc  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__8()
0x18c2  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x18c7  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x18cc  ret
0x18cd  ldarg.0
0x18ce  ldloc.0
0x18cf  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__9()
0x18d5  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x18da  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x18df  ret
0x18e0  ldarg.0
0x18e1  ldloc.0
0x18e2  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__10()
0x18e8  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x18ed  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x18f2  ret
0x18f3  ldarg.0
0x18f4  ldloc.0
0x18f5  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__11()
0x18fb  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1900  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1905  ret
0x1906  ldarg.0
0x1907  ldloc.0
0x1908  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__12()
0x190e  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1913  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1918  ret
0x1919  ldarg.0
0x191a  ldloc.0
0x191b  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__13()
0x1921  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1926  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x192b  ret
0x192c  ldarg.0
0x192d  ldloc.0
0x192e  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__14()
0x1934  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1939  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x193e  ret
0x193f  ldarg.0
0x1940  ldloc.0
0x1941  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__15()
0x1947  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x194c  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1951  ret
0x1952  ldarg.0
0x1953  ldloc.0
0x1954  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__16()
0x195a  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x195f  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1964  ret
0x1965  ldarg.0
0x1966  ldloc.0
0x1967  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__17()
0x196d  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1972  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x1977  ret
0x1978  ldarg.0
0x1979  ldloc.0
0x197a  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__18()
0x1980  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1985  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x198a  ret
0x198b  ldarg.0
0x198c  ldloc.0
0x198d  ldftn    instance bool <>c__DisplayClass21_0::<CompareObjects>b__19()
0x1993  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1998  call     instance bool Microsoft.ReportingServices.RdlExpressions.SafeExpressions.Utils.SafeExpressionsAndLegacyComparison::CompareForMismatch(class [mscorlib]System.Func`1<bool> comparisonFunc)
0x199d  ret
0x199e  ldstr    aUnknownTypecod// "Unknown TypeCode {0}"
0x19a3  ldloc.2
0x19a4  box      [mscorlib]System.TypeCode
0x19a9  call     string [mscorlib]System.String::Format(string, object)
0x19ae  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x19b3  throw
```
