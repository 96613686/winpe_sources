# Microsoft.ReportingServices.Library.ItemSearchConditions::.ctor

- ea: `0x130c0`
- end: `0x13558`
- name: `Microsoft.ReportingServices.Library.ItemSearchConditions::.ctor`
- size: `1176`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a580`

## callees

- `0x13080`
- `0x130c0`
- `0x135c0`
- `0x135e0`
- `0x13670`
- `0x137c0`
- `0x137e0`
- `0x87e70`
- `0x87e90`

## string_xrefs

- `0x130c9`: `ComponentID`
- `0x134be`: `ComponentID`
- `0x132ed`: `ComponentLookup`
- `0x1347a`: `ComponentLookup`
- `0x1336b`: `condition compatLevel`

## pseudocode

```c

```

## disassembly

```asm
0x130c0  ldarg.0
0x130c1  ldc.i4.2
0x130c2  newarr   [mscorlib]System.String
0x130c7  dup
0x130c8  ldc.i4.0
0x130c9  ldstr    aComponentid_0// "ComponentID"
0x130ce  stelem.ref
0x130cf  dup
0x130d0  ldc.i4.1
0x130d1  ldstr    aType_0// "Type"
0x130d6  stelem.ref
0x130d7  stfld    string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_requiredComponentLookupProperties
0x130dc  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x130e1  stloc.0
0x130e2  ldloc.0
0x130e3  ldarg.2
0x130e4  stfld    class Microsoft.ReportingServices.Library.ItemSearchOptions <>c__DisplayClass0_0::options
0x130e9  ldarg.0
0x130ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::.ctor()
0x130ef  ldarg.1
0x130f0  brfalse.s loc_130F6
0x130f2  ldarg.1
0x130f3  ldlen
0x130f4  brtrue.s loc_130F7
0x130f6  ret
0x130f7  ldc.i4.0
0x130f8  stloc.1
0x130f9  ldc.i4.0
0x130fa  stloc.2
0x130fb  br       loc_1354E
0x13100  newobj   instance void <>c__DisplayClass0_1::.ctor()
0x13105  stloc.3
0x13106  ldloc.3
0x13107  ldloc.0
0x13108  stfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x1310d  ldarg.1
0x1310e  ldloc.2
0x1310f  ldelem.ref
0x13110  stloc.s  4
0x13112  ldloc.s  4
0x13114  brtrue.s loc_13121
0x13116  ldstr    aSearchconditio// "SearchCondition"
0x1311b  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x13120  throw
0x13121  ldloc.3
0x13122  ldloc.s  4
0x13124  ldfld    string Microsoft.ReportingServices.Library.Soap2010.SearchCondition::Name
0x13129  stfld    string <>c__DisplayClass0_1::name
0x1312e  ldloc.s  4
0x13130  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Library.Soap2010.SearchCondition::Values
0x13135  stloc.s  5
0x13137  ldnull
0x13138  stloc.s  6
0x1313a  ldloc.3
0x1313b  ldfld    string <>c__DisplayClass0_1::name
0x13140  brtrue.s loc_1314D
0x13142  ldstr    aName// "Name"
0x13147  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x1314c  throw
0x1314d  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.ItemSearchConditions::SearchableProperties
0x13152  ldloc.3
0x13153  ldfld    string <>c__DisplayClass0_1::name
0x13158  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x1315d  castclass [mscorlib]System.String
0x13162  stloc.s  6
0x13164  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x13169  ldloc.3
0x1316a  ldfld    string <>c__DisplayClass0_1::name
0x1316f  ldstr    aAll// "All"
0x13174  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0x13179  brtrue.s loc_13182
0x1317b  ldstr    aAll// "All"
0x13180  stloc.s  6
0x13182  ldloc.s  6
0x13184  brtrue.s loc_13192
0x13186  ldloc.3
0x13187  ldfld    string <>c__DisplayClass0_1::name
0x1318c  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x13191  throw
0x13192  ldarg.0
0x13193  ldloc.s  6
0x13195  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::ContainsKey(var<u1>)
0x1319a  brfalse.s loc_131AE
0x1319c  ldloc.3
0x1319d  ldfld    string <>c__DisplayClass0_1::name
0x131a2  ldloc.3
0x131a3  ldfld    string <>c__DisplayClass0_1::name
0x131a8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x131ad  throw
0x131ae  ldloc.s  6
0x131b0  ldstr    aAll// "All"
0x131b5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x131ba  brfalse.s loc_13217
0x131bc  ldloc.3
0x131bd  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x131c2  ldfld    class Microsoft.ReportingServices.Library.ItemSearchOptions <>c__DisplayClass0_0::options
0x131c7  callvirt instance valuetype Microsoft.ReportingServices.Library.ServerCompatLevel Microsoft.ReportingServices.Library.ItemSearchOptions::get_CompatLevel()
0x131cc  ldc.i4.1
0x131cd  bge.s    loc_131DB
0x131cf  ldloc.3
0x131d0  ldfld    string <>c__DisplayClass0_1::name
0x131d5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x131da  throw
0x131db  ldc.i4.1
0x131dc  stloc.1
0x131dd  ldsfld   string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_textPropertyNames
0x131e2  stloc.s  8
0x131e4  ldc.i4.0
0x131e5  stloc.s  9
0x131e7  br.s     loc_1320D
0x131e9  ldloc.s  8
0x131eb  ldloc.s  9
0x131ed  ldelem.ref
0x131ee  stloc.s  0xA
0x131f0  ldarg.0
0x131f1  ldloc.s  0xA
0x131f3  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::ContainsKey(var<u1>)
0x131f8  brfalse.s loc_13207
0x131fa  ldloc.s  0xA
0x131fc  ldstr    aAll// "All"
0x13201  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x13206  throw
0x13207  ldloc.s  9
0x13209  ldc.i4.1
0x1320a  add
0x1320b  stloc.s  9
0x1320d  ldloc.s  9
0x1320f  ldloc.s  8
0x13211  ldlen
0x13212  conv.i4
0x13213  blt.s    loc_131E9
0x13215  br.s     loc_13257
0x13217  ldloc.1
0x13218  brfalse.s loc_13257
0x1321a  ldsfld   string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_textPropertyNames
0x1321f  stloc.s  8
0x13221  ldc.i4.0
0x13222  stloc.s  9
0x13224  br.s     loc_1324F
0x13226  ldloc.s  8
0x13228  ldloc.s  9
0x1322a  ldelem.ref
0x1322b  stloc.s  0xB
0x1322d  ldloc.s  6
0x1322f  ldloc.s  0xB
0x13231  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13236  brfalse.s loc_13249
0x13238  ldstr    aAll// "All"
0x1323d  ldloc.3
0x1323e  ldfld    string <>c__DisplayClass0_1::name
0x13243  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x13248  throw
0x13249  ldloc.s  9
0x1324b  ldc.i4.1
0x1324c  add
0x1324d  stloc.s  9
0x1324f  ldloc.s  9
0x13251  ldloc.s  8
0x13253  ldlen
0x13254  conv.i4
0x13255  blt.s    loc_13226
0x13257  ldloc.s  5
0x13259  brtrue.s loc_13267
0x1325b  ldloc.3
0x1325c  ldfld    string <>c__DisplayClass0_1::name
0x13261  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x13266  throw
0x13267  ldloc.s  5
0x13269  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x1326e  stloc.s  0xC
0x13270  br.s     loc_13287
0x13272  ldloca.s 0xC
0x13274  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x13279  brtrue.s loc_13287
0x1327b  ldloc.3
0x1327c  ldfld    string <>c__DisplayClass0_1::name
0x13281  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x13286  throw
0x13287  ldloca.s 0xC
0x13289  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x1328e  brtrue.s loc_13272
0x13290  leave.s  loc_132A0
0x13292  ldloca.s 0xC
0x13294  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x1329a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1329f  endfinally
0x132a0  newobj   instance void Microsoft.ReportingServices.Library.ItemSearchCondition::.ctor()
0x132a5  stloc.s  7
0x132a7  ldloc.s  7
0x132a9  ldloc.s  4
0x132ab  ldfld    bool Microsoft.ReportingServices.Library.Soap2010.SearchCondition::ConditionSpecified
0x132b0  brtrue.s loc_132C6
0x132b2  ldloc.s  6
0x132b4  ldstr    aType_0// "Type"
0x132b9  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x132be  brtrue.s loc_132C3
0x132c0  ldc.i4.1
0x132c1  br.s     loc_132CD
0x132c3  ldc.i4.0
0x132c4  br.s     loc_132CD
0x132c6  ldloc.s  4
0x132c8  ldfld    valuetype Microsoft.ReportingServices.Library.Soap2010.ConditionEnum Microsoft.ReportingServices.Library.Soap2010.SearchCondition::Condition
0x132cd  stfld    valuetype Microsoft.ReportingServices.Library.Soap2010.ConditionEnum Microsoft.ReportingServices.Library.ItemSearchCondition::Condition
0x132d2  ldloc.3
0x132d3  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x132d8  ldfld    class Microsoft.ReportingServices.Library.ItemSearchOptions <>c__DisplayClass0_0::options
0x132dd  callvirt instance bool Microsoft.ReportingServices.Library.ItemSearchOptions::get_ComponentLookup()
0x132e2  brfalse.s loc_132FA
0x132e4  ldloc.s  6
0x132e6  call     bool Microsoft.ReportingServices.Library.ItemSearchConditions::IsFieldValidForComponentLookup(string normalizedName)
0x132eb  brtrue.s loc_132FA
0x132ed  ldstr    aComponentlooku// "ComponentLookup"
0x132f2  ldloc.s  6
0x132f4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x132f9  throw
0x132fa  ldloc.s  7
0x132fc  ldfld    valuetype Microsoft.ReportingServices.Library.Soap2010.ConditionEnum Microsoft.ReportingServices.Library.ItemSearchCondition::Condition
0x13301  ldloc.s  6
0x13303  ldloc.3
0x13304  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x13309  ldfld    class Microsoft.ReportingServices.Library.ItemSearchOptions <>c__DisplayClass0_0::options
0x1330e  call     bool Microsoft.ReportingServices.Library.ItemSearchConditions::IsConditionSupported(valuetype Microsoft.ReportingServices.Library.Soap2010.ConditionEnum condition, string normalizedName, class Microsoft.ReportingServices.Library.ItemSearchOptions searchOptions)
0x13313  brtrue.s loc_13333
0x13315  ldloc.3
0x13316  ldfld    string <>c__DisplayClass0_1::name
0x1331b  ldloc.s  7
0x1331d  ldflda   valuetype Microsoft.ReportingServices.Library.Soap2010.ConditionEnum Microsoft.ReportingServices.Library.ItemSearchCondition::Condition
0x13322  constrained. Microsoft.ReportingServices.Library.Soap2010.ConditionEnum
0x13328  callvirt instance string [mscorlib]System.Object::ToString()
0x1332d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementCombinationException::.ctor(string, string)
0x13332  throw
0x13333  ldloc.s  7
0x13335  ldloc.s  5
0x13337  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Library.ItemSearchCondition::Values
0x1333c  ldloc.s  7
0x1333e  ldfld    valuetype Microsoft.ReportingServices.Library.Soap2010.ConditionEnum Microsoft.ReportingServices.Library.ItemSearchCondition::Condition
0x13343  ldc.i4.2
0x13344  beq.s    loc_13350
0x13346  ldloc.s  4
0x13348  ldfld    valuetype Microsoft.ReportingServices.Library.Soap2010.ConditionEnum Microsoft.ReportingServices.Library.Soap2010.SearchCondition::Condition
0x1334d  ldc.i4.3
0x1334e  bne.un.s loc_133B4
0x13350  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x13355  ldloc.3
0x13356  ldfld    class <>c__DisplayClass0_0 <>c__DisplayClass0_1::CS$<>8__locals1
0x1335b  ldfld    class Microsoft.ReportingServices.Library.ItemSearchOptions <>c__DisplayClass0_0::options
0x13360  callvirt instance valuetype Microsoft.ReportingServices.Library.ServerCompatLevel Microsoft.ReportingServices.Library.ItemSearchOptions::get_CompatLevel()
0x13365  ldc.i4.1
0x13366  clt
0x13368  ldc.i4.0
0x13369  ceq
0x1336b  ldstr    aConditionCompa// "condition compatLevel"
0x13370  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x13375  ldloc.s  7
0x13377  ldfld    valuetype Microsoft.ReportingServices.Library.Soap2010.ConditionEnum Microsoft.ReportingServices.Library.ItemSearchCondition::Condition
0x1337c  ldc.i4.3
0x1337d  bne.un.s loc_1339A
0x1337f  ldloc.s  7
0x13381  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Library.ItemSearchCondition::Values
0x13386  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x1338b  ldc.i4.2
0x1338c  beq.s    loc_133CF
0x1338e  ldloc.3
0x1338f  ldfld    string <>c__DisplayClass0_1::name
0x13394  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x13399  throw
0x1339a  ldloc.s  7
0x1339c  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Library.ItemSearchCondition::Values
0x133a1  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x133a6  brtrue.s loc_133CF
0x133a8  ldloc.3
0x133a9  ldfld    string <>c__DisplayClass0_1::name
0x133ae  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x133b3  throw
0x133b4  ldloc.s  7
0x133b6  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Library.ItemSearchCondition::Values
0x133bb  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x133c0  ldc.i4.1
0x133c1  beq.s    loc_133CF
0x133c3  ldloc.3
0x133c4  ldfld    string <>c__DisplayClass0_1::name
0x133c9  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x133ce  throw
0x133cf  ldloc.s  7
0x133d1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Library.ItemSearchCondition::Values
0x133d6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x133db  stloc.s  0xD
0x133dd  br.s     loc_133FE
0x133df  ldloc.s  0xD
0x133e1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x133e6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x133eb  ldc.i4   0x80
0x133f0  ble.s    loc_133FE
0x133f2  ldloc.3
0x133f3  ldfld    string <>c__DisplayClass0_1::name
0x133f8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x133fd  throw
0x133fe  ldloc.s  0xD
0x13400  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13405  brtrue.s loc_133DF
  ... truncated ...
```
