# Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForDateRange

- ea: `0x584c0`
- end: `0x586fe`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::GetFilterForDateRange`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x58700`

## callees

- `0x32ea0`
- `0x53f00`
- `0x584c0`

## string_xrefs

- `0x5856b`: `TimeCreated[timediff(@SystemTime) <= `
- `0x586eb`: `TimeCreated[`

## pseudocode

```c

```

## disassembly

```asm
0x584c0  ldc.i4.0
0x584c1  conv.i8
0x584c2  stloc.0
0x584c3  ldarg.0
0x584c4  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x584c9  brtrue.s loc_584FC
0x584cb  ldarg.2
0x584cc  ldind.ref
0x584cd  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::RelativeTimeInfo
0x584d2  ldarg.0
0x584d3  ldflda   int32 Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::curPeriodSelected
0x584d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x584dd  ldtoken  [mscorlib]System.Int32
0x584e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x584e7  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x584ec  castclass [mscorlib]System.IFormatProvider
0x584f1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x584f6  ldc.i4.1
0x584f7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::SetProperty(string propertyName, string value, bool simple)
0x584fc  ldarg.0
0x584fd  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::curPeriodSelected
0x58502  stloc.1
0x58503  ldloc.1
0x58504  ldc.i4.1
0x58505  sub
0x58506  switch   loc_58545, loc_58521, loc_5852A, loc_5853C, loc_58533
0x5851f  br.s     loc_5854C
0x58521  ldc.i4   0x2932E00
0x58526  conv.i8
0x58527  stloc.0
0x58528  br.s     loc_5854C
0x5852a  ldc.i4   0x5265C00
0x5852f  conv.i8
0x58530  stloc.0
0x58531  br.s     loc_5854C
0x58533  ldc.i4   0x9A7EC800
0x58538  conv.u8
0x58539  stloc.0
0x5853a  br.s     loc_5854C
0x5853c  ldc.i4   0x240C8400
0x58541  conv.i8
0x58542  stloc.0
0x58543  br.s     loc_5854C
0x58545  ldc.i4   0x36EE80
0x5854a  conv.i8
0x5854b  stloc.0
0x5854c  ldloc.0
0x5854d  ldc.i4.0
0x5854e  conv.i8
0x5854f  ble.un.s loc_585B2
0x58551  ldarg.1
0x58552  ldind.ref
0x58553  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x58558  brtrue.s loc_58568
0x5855a  ldarg.1
0x5855b  ldarg.1
0x5855c  ldind.ref
0x5855d  ldstr    aAnd// " and "
0x58562  call     string [mscorlib]System.String::Concat(string, string)
0x58567  stind.ref
0x58568  ldarg.1
0x58569  ldarg.1
0x5856a  ldind.ref
0x5856b  ldstr    aTimecreatedTim// "TimeCreated[timediff(@SystemTime) <= "
0x58570  call     string [mscorlib]System.String::Concat(string, string)
0x58575  stind.ref
0x58576  ldarg.1
0x58577  ldarg.1
0x58578  ldind.ref
0x58579  ldloca.s 0
0x5857b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x58580  ldtoken  [mscorlib]System.UInt64
0x58585  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5858a  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x5858f  castclass [mscorlib]System.IFormatProvider
0x58594  call     instance string [mscorlib]System.UInt64::ToString(class [mscorlib]System.IFormatProvider)
0x58599  call     string [mscorlib]System.String::Concat(string, string)
0x5859e  stind.ref
0x5859f  ldarg.1
0x585a0  ldarg.1
0x585a1  ldind.ref
0x585a2  ldstr    asc_B52B0// "]"
0x585a7  call     string [mscorlib]System.String::Concat(string, string)
0x585ac  stind.ref
0x585ad  br       loc_586FC
0x585b2  ldarg.0
0x585b3  ldfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::curPeriodSelected
0x585b8  ldc.i4.5
0x585b9  ble      loc_586FC
0x585be  ldc.i4.0
0x585bf  stloc.2
0x585c0  ldsfld   string [mscorlib]System.String::Empty
0x585c5  stloc.3
0x585c6  ldsfld   string [mscorlib]System.String::Empty
0x585cb  stloc.s  4
0x585cd  ldarg.0
0x585ce  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::dtStartTime
0x585d3  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x585d8  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x585dd  brfalse.s loc_58642
0x585df  ldarg.0
0x585e0  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::dtStartTime
0x585e5  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetCrimsonDateTime(valuetype [mscorlib]System.DateTime dt)
0x585ea  stloc.s  4
0x585ec  ldarg.0
0x585ed  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x585f2  brtrue.s loc_5862E
0x585f4  ldarg.2
0x585f5  ldind.ref
0x585f6  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::FromDate
0x585fb  ldarg.0
0x585fc  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::dtStartTime
0x58601  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x58606  stloc.s  5
0x58608  ldloca.s 5
0x5860a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x5860f  ldtoken  [mscorlib]System.Int64
0x58614  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x58619  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x5861e  castclass [mscorlib]System.IFormatProvider
0x58623  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x58628  ldc.i4.1
0x58629  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::SetProperty(string propertyName, string value, bool simple)
0x5862e  ldstr    aSystemtime// "@SystemTime>='"
0x58633  ldloc.s  4
0x58635  ldstr    asc_AC650// "'"
0x5863a  call     string [mscorlib]System.String::Concat(string, string, string)
0x5863f  stloc.3
0x58640  ldc.i4.1
0x58641  stloc.2
0x58642  ldarg.0
0x58643  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::dtEndTime
0x58648  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5864d  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x58652  brfalse.s loc_586CE
0x58654  ldarg.0
0x58655  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::dtEndTime
0x5865a  call     string Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::GetCrimsonDateTime(valuetype [mscorlib]System.DateTime dt)
0x5865f  stloc.s  4
0x58661  ldloc.3
0x58662  ldloc.2
0x58663  brtrue.s loc_5866C
0x58665  ldstr    asc_AA3F4// ""
0x5866a  br.s     loc_58671
0x5866c  ldstr    aAnd// " and "
0x58671  call     string [mscorlib]System.String::Concat(string, string)
0x58676  stloc.3
0x58677  ldloc.3
0x58678  ldstr    aSystemtime_0// "@SystemTime<='"
0x5867d  ldloc.s  4
0x5867f  ldstr    asc_AC650// "'"
0x58684  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x58689  stloc.3
0x5868a  ldarg.0
0x5868b  ldfld    bool Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::isUserQuery
0x58690  brtrue.s loc_586CC
0x58692  ldarg.2
0x58693  ldind.ref
0x58694  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.StandardStringValues::ToDate
0x58699  ldarg.0
0x5869a  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Windows.ManagementUI.CombinedControls.QueryFilter::dtEndTime
0x5869f  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x586a4  stloc.s  5
0x586a6  ldloca.s 5
0x586a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x586ad  ldtoken  [mscorlib]System.Int64
0x586b2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x586b7  callvirt instance object [mscorlib]System.Globalization.CultureInfo::GetFormat(class [mscorlib]System.Type)
0x586bc  castclass [mscorlib]System.IFormatProvider
0x586c1  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x586c6  ldc.i4.1
0x586c7  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.QueryConfig::SetProperty(string propertyName, string value, bool simple)
0x586cc  ldc.i4.1
0x586cd  stloc.2
0x586ce  ldloc.2
0x586cf  brfalse.s loc_586FC
0x586d1  ldarg.1
0x586d2  ldind.ref
0x586d3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x586d8  brtrue.s loc_586E8
0x586da  ldarg.1
0x586db  ldarg.1
0x586dc  ldind.ref
0x586dd  ldstr    aAnd// " and "
0x586e2  call     string [mscorlib]System.String::Concat(string, string)
0x586e7  stind.ref
0x586e8  ldarg.1
0x586e9  ldarg.1
0x586ea  ldind.ref
0x586eb  ldstr    aTimecreated// "TimeCreated["
0x586f0  ldloc.3
0x586f1  ldstr    asc_B52B0// "]"
0x586f6  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x586fb  stind.ref
0x586fc  ldc.i4.1
0x586fd  ret
```
