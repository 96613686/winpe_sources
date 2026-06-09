# Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiDataItem

- ea: `0xf10`
- end: `0x10a6`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateKpiDataItem`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1200`

## callees

- `0xf10`
- `0x1130`

## string_xrefs

- `0xf93`: `{0}.Path`

## pseudocode

```c

```

## disassembly

```asm
0xf10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf15  ldstr    a0Type// "{0}.Type"
0xf1a  ldarg.1
0xf1b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xf20  stloc.0
0xf21  ldarg.2
0xf22  ldloc.0
0xf23  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0xf28  brfalse  loc_10A4
0xf2d  ldarg.2
0xf2e  ldloc.0
0xf2f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0xf34  ldloca.s 1
0xf36  call     T0x2B000005
0xf3b  brfalse  loc_10A4
0xf40  ldloc.1
0xf41  brtrue.s loc_F7D
0xf43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf48  ldstr    a0Value// "{0}.Value"
0xf4d  ldarg.1
0xf4e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xf53  stloc.s  9
0xf55  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem::.ctor()
0xf5a  dup
0xf5b  ldc.i4.0
0xf5c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType)
0xf61  dup
0xf62  ldarg.2
0xf63  ldloc.s  9
0xf65  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0xf6a  brtrue.s loc_F6F
0xf6c  ldnull
0xf6d  br.s     loc_F77
0xf6f  ldarg.2
0xf70  ldloc.s  9
0xf72  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0xf77  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiStaticDataItem::set_Value(string)
0xf7c  ret
0xf7d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf82  ldstr    a0Id// "{0}.Id"
0xf87  ldarg.1
0xf88  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xf8d  stloc.2
0xf8e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf93  ldstr    a0Path// "{0}.Path"
0xf98  ldarg.1
0xf99  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xf9e  stloc.3
0xf9f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfa4  ldstr    a0Column// "{0}.Column"
0xfa9  ldarg.1
0xfaa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xfaf  stloc.s  4
0xfb1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfb6  ldstr    a0Aggregation// "{0}.Aggregation"
0xfbb  ldarg.1
0xfbc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xfc1  stloc.s  5
0xfc3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfc8  ldstr    a0Parameters// "{0}.Parameters"
0xfcd  ldarg.1
0xfce  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xfd3  stloc.s  6
0xfd5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xfda  stloc.s  7
0xfdc  ldarg.2
0xfdd  ldloc.2
0xfde  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0xfe3  brfalse.s loc_FF4
0xfe5  ldarg.2
0xfe6  ldloc.2
0xfe7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0xfec  ldloca.s 7
0xfee  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xff3  pop
0xff4  ldc.i4.0
0xff5  stloc.s  8
0xff7  ldarg.2
0xff8  ldloc.s  5
0xffa  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0xfff  brfalse.s loc_1011
0x1001  ldarg.2
0x1002  ldloc.s  5
0x1004  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x1009  ldloca.s 8
0x100b  call     T0x2B000006
0x1010  pop
0x1011  ldarg.1
0x1012  ldstr    aTrendset// "TrendSet"
0x1017  call     bool [mscorlib]System.String::op_Equality(string, string)
0x101c  brfalse.s loc_1023
0x101e  ldc.i4.0
0x101f  stloc.s  8
0x1021  br.s     loc_102A
0x1023  ldloc.s  8
0x1025  brtrue.s loc_102A
0x1027  ldc.i4.1
0x1028  stloc.s  8
0x102a  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::.ctor()
0x102f  dup
0x1030  ldc.i4.1
0x1031  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType)
0x1036  dup
0x1037  ldarg.2
0x1038  ldloc.s  4
0x103a  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x103f  brtrue.s loc_1044
0x1041  ldnull
0x1042  br.s     loc_104C
0x1044  ldarg.2
0x1045  ldloc.s  4
0x1047  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x104c  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::set_Column(string)
0x1051  dup
0x1052  ldloc.s  7
0x1054  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::set_Id(valuetype [mscorlib]System.Guid)
0x1059  dup
0x105a  ldarg.2
0x105b  ldloc.3
0x105c  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x1061  brtrue.s loc_1066
0x1063  ldnull
0x1064  br.s     loc_106D
0x1066  ldarg.2
0x1067  ldloc.3
0x1068  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x106d  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::set_Path(string)
0x1072  dup
0x1073  ldloc.s  8
0x1075  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::set_Aggregation(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation)
0x107a  dup
0x107b  ldarg.2
0x107c  ldloc.s  6
0x107e  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x1083  brtrue.s loc_1090
0x1085  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>::.ctor()
0x108a  stloc.s  0xA
0x108c  ldloc.s  0xA
0x108e  br.s     loc_109E
0x1090  ldarg.0
0x1091  ldarg.2
0x1092  ldloc.s  6
0x1094  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x1099  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> Microsoft.ReportingServices.Portal.Repositories.CatalogItemFactory::CreateDataSetParameters(string parameterString)
0x109e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::set_Parameters(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>)
0x10a3  ret
0x10a4  ldnull
0x10a5  ret
```
