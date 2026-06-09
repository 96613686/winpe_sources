# System.Windows.PropertyPath::ResolveIndexerParams_0

- ea: `0x194e0`
- end: `0x19728`
- name: `System.Windows.PropertyPath::ResolveIndexerParams_0`
- size: `584`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18e30`
- `0x19180`

## callees

- `0x18c10`
- `0x194e0`
- `0x19730`
- `0x197b0`
- `0x38c70`

## string_xrefs

- `0x195d2`: `PathParametersIndexOutOfRange`
- `0x195ad`: `PathParameterIsNull`
- `0x196a3`: `PropertyPathIndexWrongType`

## pseudocode

```c

```

## disassembly

```asm
0x194e0  ldarg.1
0x194e1  callvirt instance int32 class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Count()
0x194e6  newarr   System.Windows.IndexerParameterInfo
0x194eb  stloc.0
0x194ec  ldc.i4.0
0x194ed  stloc.1
0x194ee  br       loc_1971D
0x194f3  ldarg.1
0x194f4  ldloc.1
0x194f5  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x194fa  ldfld    string MS.Internal.Data.IndexerParamInfo::parenString
0x194ff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19504  brfalse.s loc_19523
0x19506  ldloc.0
0x19507  ldloc.1
0x19508  ldelema  System.Windows.IndexerParameterInfo
0x1950d  ldarg.1
0x1950e  ldloc.1
0x1950f  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x19514  ldfld    string MS.Internal.Data.IndexerParamInfo::valueString
0x19519  stfld    object System.Windows.IndexerParameterInfo::value
0x1951e  br       loc_19719
0x19523  ldarg.1
0x19524  ldloc.1
0x19525  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x1952a  ldfld    string MS.Internal.Data.IndexerParamInfo::valueString
0x1952f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19534  brfalse  loc_19630
0x19539  ldarg.1
0x1953a  ldloc.1
0x1953b  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x19540  ldfld    string MS.Internal.Data.IndexerParamInfo::parenString
0x19545  callvirt instance string [mscorlib]System.String::Trim()
0x1954a  ldc.i4.7
0x1954b  call     class [mscorlib]System.Globalization.CultureInfo [WindowsBase]System.Windows.Markup.TypeConverterHelper::get_InvariantEnglishUS()
0x19550  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0x19555  ldloca.s 2
0x19557  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x1955c  brfalse  loc_19604
0x19561  ldc.i4.0
0x19562  ldloc.2
0x19563  bgt.s    loc_195CC
0x19565  ldloc.2
0x19566  ldarg.0
0x19567  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<object> System.Windows.PropertyPath::get_PathParameters()
0x1956c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::get_Count()
0x19571  bge.s    loc_195CC
0x19573  ldarg.0
0x19574  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<object> System.Windows.PropertyPath::get_PathParameters()
0x19579  ldloc.2
0x1957a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::get_Item(!!T0)
0x1957f  stloc.3
0x19580  ldloc.3
0x19581  brfalse.s loc_195A7
0x19583  ldloc.0
0x19584  ldloc.1
0x19585  ldelema  System.Windows.IndexerParameterInfo
0x1958a  ldloc.3
0x1958b  stfld    object System.Windows.IndexerParameterInfo::value
0x19590  ldloc.0
0x19591  ldloc.1
0x19592  ldelema  System.Windows.IndexerParameterInfo
0x19597  ldloc.3
0x19598  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1959d  stfld    class [mscorlib]System.Type System.Windows.IndexerParameterInfo::type
0x195a2  br       loc_19719
0x195a7  ldarg.3
0x195a8  brfalse  loc_19719
0x195ad  ldstr    aPathparameteri// "PathParameterIsNull"
0x195b2  ldc.i4.1
0x195b3  newarr   [mscorlib]System.Object
0x195b8  dup
0x195b9  ldc.i4.0
0x195ba  ldloc.2
0x195bb  box      [mscorlib]System.Int32
0x195c0  stelem.ref
0x195c1  call     string System.Windows.SR::Get(string id, object[] args)
0x195c6  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x195cb  throw
0x195cc  ldarg.3
0x195cd  brfalse  loc_19719
0x195d2  ldstr    aPathparameters// "PathParametersIndexOutOfRange"
0x195d7  ldc.i4.2
0x195d8  newarr   [mscorlib]System.Object
0x195dd  dup
0x195de  ldc.i4.0
0x195df  ldloc.2
0x195e0  box      [mscorlib]System.Int32
0x195e5  stelem.ref
0x195e6  dup
0x195e7  ldc.i4.1
0x195e8  ldarg.0
0x195e9  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<object> System.Windows.PropertyPath::get_PathParameters()
0x195ee  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::get_Count()
0x195f3  box      [mscorlib]System.Int32
0x195f8  stelem.ref
0x195f9  call     string System.Windows.SR::Get(string id, object[] args)
0x195fe  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x19603  throw
0x19604  ldloc.0
0x19605  ldloc.1
0x19606  ldelema  System.Windows.IndexerParameterInfo
0x1960b  ldstr    asc_28D9CE// "("
0x19610  ldarg.1
0x19611  ldloc.1
0x19612  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x19617  ldfld    string MS.Internal.Data.IndexerParamInfo::parenString
0x1961c  ldstr    asc_28A064// ")"
0x19621  call     string [mscorlib]System.String::Concat(string, string, string)
0x19626  stfld    object System.Windows.IndexerParameterInfo::value
0x1962b  br       loc_19719
0x19630  ldloc.0
0x19631  ldloc.1
0x19632  ldelema  System.Windows.IndexerParameterInfo
0x19637  ldarg.0
0x19638  ldarg.1
0x19639  ldloc.1
0x1963a  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x1963f  ldfld    string MS.Internal.Data.IndexerParamInfo::parenString
0x19644  ldarg.2
0x19645  call     instance class [mscorlib]System.Type System.Windows.PropertyPath::GetTypeFromName(string name, object context)
0x1964a  stfld    class [mscorlib]System.Type System.Windows.IndexerParameterInfo::type
0x1964f  ldloc.0
0x19650  ldloc.1
0x19651  ldelema  System.Windows.IndexerParameterInfo
0x19656  ldfld    class [mscorlib]System.Type System.Windows.IndexerParameterInfo::type
0x1965b  ldnull
0x1965c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x19661  brfalse  loc_196E6
0x19666  ldarg.0
0x19667  ldarg.1
0x19668  ldloc.1
0x19669  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x1966e  ldfld    string MS.Internal.Data.IndexerParamInfo::valueString
0x19673  callvirt instance string [mscorlib]System.String::Trim()
0x19678  ldloc.0
0x19679  ldloc.1
0x1967a  ldelema  System.Windows.IndexerParameterInfo
0x1967f  ldfld    class [mscorlib]System.Type System.Windows.IndexerParameterInfo::type
0x19684  ldarg.3
0x19685  call     instance object System.Windows.PropertyPath::GetTypedParamValue(string param, class [mscorlib]System.Type type, bool throwOnError)
0x1968a  stloc.s  4
0x1968c  ldloc.s  4
0x1968e  brfalse.s loc_196A0
0x19690  ldloc.0
0x19691  ldloc.1
0x19692  ldelema  System.Windows.IndexerParameterInfo
0x19697  ldloc.s  4
0x19699  stfld    object System.Windows.IndexerParameterInfo::value
0x1969e  br.s     loc_19719
0x196a0  ldarg.3
0x196a1  brfalse.s loc_196D7
0x196a3  ldstr    aPropertypathin_0// "PropertyPathIndexWrongType"
0x196a8  ldc.i4.2
0x196a9  newarr   [mscorlib]System.Object
0x196ae  dup
0x196af  ldc.i4.0
0x196b0  ldarg.1
0x196b1  ldloc.1
0x196b2  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x196b7  ldfld    string MS.Internal.Data.IndexerParamInfo::parenString
0x196bc  stelem.ref
0x196bd  dup
0x196be  ldc.i4.1
0x196bf  ldarg.1
0x196c0  ldloc.1
0x196c1  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x196c6  ldfld    string MS.Internal.Data.IndexerParamInfo::valueString
0x196cb  stelem.ref
0x196cc  call     string System.Windows.SR::Get(string id, object[] args)
0x196d1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x196d6  throw
0x196d7  ldloc.0
0x196d8  ldloc.1
0x196d9  ldelema  System.Windows.IndexerParameterInfo
0x196de  ldnull
0x196df  stfld    class [mscorlib]System.Type System.Windows.IndexerParameterInfo::type
0x196e4  br.s     loc_19719
0x196e6  ldloc.0
0x196e7  ldloc.1
0x196e8  ldelema  System.Windows.IndexerParameterInfo
0x196ed  ldstr    asc_28D9CE// "("
0x196f2  ldarg.1
0x196f3  ldloc.1
0x196f4  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x196f9  ldfld    string MS.Internal.Data.IndexerParamInfo::parenString
0x196fe  ldstr    asc_28A064// ")"
0x19703  ldarg.1
0x19704  ldloc.1
0x19705  callvirt instance var<u1> class [WindowsBase]MS.Utility.FrugalObjectList`1<valuetype MS.Internal.Data.IndexerParamInfo>::get_Item(!!T0)
0x1970a  ldfld    string MS.Internal.Data.IndexerParamInfo::valueString
0x1970f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x19714  stfld    object System.Windows.IndexerParameterInfo::value
0x19719  ldloc.1
0x1971a  ldc.i4.1
0x1971b  add
0x1971c  stloc.1
0x1971d  ldloc.1
0x1971e  ldloc.0
0x1971f  ldlen
0x19720  conv.i4
0x19721  blt      loc_194F3
0x19726  ldloc.0
0x19727  ret
```
