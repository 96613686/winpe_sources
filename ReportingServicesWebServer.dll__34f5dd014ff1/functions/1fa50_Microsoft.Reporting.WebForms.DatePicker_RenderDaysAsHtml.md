# Microsoft.Reporting.WebForms.DatePicker::RenderDaysAsHtml

- ea: `0x1fa50`
- end: `0x1ff86`
- name: `Microsoft.Reporting.WebForms.DatePicker::RenderDaysAsHtml`
- size: `1334`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1f3b0`

## callees

- `0x1d520`
- `0x1d5a0`
- `0x1d5b0`
- `0x1d5c0`
- `0x1d750`
- `0x1e870`
- `0x1eab0`
- `0x1f980`
- `0x1fa50`
- `0x1ffb0`
- `0x1ffe0`
- `0x20100`
- `0x20110`
- `0x20120`
- `0x20140`
- `0x20150`
- `0x202a0`
- `0x203e0`
- `0x20400`
- `0x20460`
- `0x20530`
- `0x216b0`
- `0x219a0`

## string_xrefs

- `0x1fcbe`: `<div class={0}><a href="javascript:MoveToDate('{2}', false)">{1}</a></div>`

## pseudocode

```c

```

## disassembly

```asm
0x1fa50  ldarg.2
0x1fa51  ldobj    Microsoft.Reporting.WebForms.SimpleDate
0x1fa56  stloc.0
0x1fa57  ldloca.s 0
0x1fa59  ldc.i4.1
0x1fa5a  call     instance void Microsoft.Reporting.WebForms.SimpleDate::set_Day(int32 value)
0x1fa5f  ldc.i4.0
0x1fa60  stloc.1
0x1fa61  ldarg.0
0x1fa62  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fa67  callvirt instance valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.DateOptions::get_CalendarType()
0x1fa6c  ldloca.s 0
0x1fa6e  ldarg.0
0x1fa6f  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fa74  callvirt instance int32 Microsoft.Reporting.WebForms.DateOptions::get_HijriAdjustment()
0x1fa79  call     int32 Microsoft.Reporting.WebForms.SPIntlCal::LocalToJulianDay(valuetype Microsoft.Reporting.WebForms.SPCalendarType calType, valuetype Microsoft.Reporting.WebForms.SimpleDate& di, int32 iAdvance)
0x1fa7e  dup
0x1fa7f  ldc.i4.1
0x1fa80  add
0x1fa81  ldc.i4.7
0x1fa82  rem
0x1fa83  stloc.2
0x1fa84  ldarg.0
0x1fa85  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fa8a  callvirt instance int32 Microsoft.Reporting.WebForms.DateOptions::get_FirstDayOfWeek()
0x1fa8f  stloc.3
0x1fa90  ldc.i4.0
0x1fa91  stloc.s  4
0x1fa93  stloc.s  5
0x1fa95  ldloc.2
0x1fa96  ldloc.3
0x1fa97  beq.s    loc_1FAE6
0x1fa99  ldloc.2
0x1fa9a  ldloc.3
0x1fa9b  sub
0x1fa9c  ldc.i4.7
0x1fa9d  add
0x1fa9e  ldc.i4.7
0x1fa9f  rem
0x1faa0  stloc.s  4
0x1faa2  ldloc.s  5
0x1faa4  ldloc.s  4
0x1faa6  sub
0x1faa7  stloc.s  5
0x1faa9  ldarg.0
0x1faaa  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1faaf  callvirt instance valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.DateOptions::get_CalendarType()
0x1fab4  ldloc.s  5
0x1fab6  call     bool Microsoft.Reporting.WebForms.SPIntlCal::IsSupportedLocalJulianDay(valuetype Microsoft.Reporting.WebForms.SPCalendarType calType, int32 jDay)
0x1fabb  brtrue.s loc_1FAC7
0x1fabd  ldloca.s 0
0x1fabf  ldc.i4.m1
0x1fac0  call     instance void Microsoft.Reporting.WebForms.SimpleDate::set_Year(int32 value)
0x1fac5  br.s     loc_1FAE6
0x1fac7  ldarg.0
0x1fac8  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1facd  callvirt instance valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.DateOptions::get_CalendarType()
0x1fad2  ldloc.s  5
0x1fad4  ldloca.s 0
0x1fad6  ldarg.0
0x1fad7  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fadc  callvirt instance int32 Microsoft.Reporting.WebForms.DateOptions::get_HijriAdjustment()
0x1fae1  call     void Microsoft.Reporting.WebForms.SPIntlCal::JulianDayToLocal(valuetype Microsoft.Reporting.WebForms.SPCalendarType calType, int32 jDay, valuetype Microsoft.Reporting.WebForms.SimpleDate& di, int32 iAdvance)
0x1fae6  ldc.i4.7
0x1fae7  ldarg.3
0x1fae8  ldloc.s  4
0x1faea  add
0x1faeb  ldc.i4.7
0x1faec  add
0x1faed  ldc.i4.1
0x1faee  sub
0x1faef  ldc.i4.7
0x1faf0  div
0x1faf1  mul
0x1faf2  stloc.s  6
0x1faf4  ldloc.s  5
0x1faf6  ldloc.s  6
0x1faf8  add
0x1faf9  ldc.i4.1
0x1fafa  sub
0x1fafb  stloc.s  7
0x1fafd  ldarg.2
0x1fafe  ldobj    Microsoft.Reporting.WebForms.SimpleDate
0x1fb03  stloc.s  8
0x1fb05  ldarg.0
0x1fb06  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fb0b  callvirt instance valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.DateOptions::get_CalendarType()
0x1fb10  ldloc.s  7
0x1fb12  call     bool Microsoft.Reporting.WebForms.SPIntlCal::IsSupportedLocalJulianDay(valuetype Microsoft.Reporting.WebForms.SPCalendarType calType, int32 jDay)
0x1fb17  brtrue.s loc_1FB23
0x1fb19  ldloca.s 8
0x1fb1b  ldc.i4.m1
0x1fb1c  call     instance void Microsoft.Reporting.WebForms.SimpleDate::set_Year(int32 value)
0x1fb21  br.s     loc_1FB42
0x1fb23  ldarg.0
0x1fb24  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fb29  callvirt instance valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.DateOptions::get_CalendarType()
0x1fb2e  ldloc.s  7
0x1fb30  ldloca.s 8
0x1fb32  ldarg.0
0x1fb33  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fb38  callvirt instance int32 Microsoft.Reporting.WebForms.DateOptions::get_HijriAdjustment()
0x1fb3d  call     void Microsoft.Reporting.WebForms.SPIntlCal::JulianDayToLocal(valuetype Microsoft.Reporting.WebForms.SPCalendarType calType, int32 jDay, valuetype Microsoft.Reporting.WebForms.SimpleDate& di, int32 iAdvance)
0x1fb42  ldloc.0
0x1fb43  stloc.s  9
0x1fb45  ldarg.0
0x1fb46  ldarg.1
0x1fb47  ldloc.s  6
0x1fb49  ldc.i4.7
0x1fb4a  div
0x1fb4b  call     instance bool Microsoft.Reporting.WebForms.DatePicker::RenderWeekHeaderAsHtml(class [mscorlib]System.Text.StringBuilder st, int32 weekCount)
0x1fb50  pop
0x1fb51  ldc.i4.0
0x1fb52  stloc.s  0xF
0x1fb54  br       loc_1FF79
0x1fb59  ldarg.1
0x1fb5a  ldstr    aTr_0// "<tr>\r"
0x1fb5f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1fb64  pop
0x1fb65  ldarg.0
0x1fb66  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bShowWeekNumber
0x1fb6b  brfalse  loc_1FD22
0x1fb70  ldloca.s 9
0x1fb72  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Year()
0x1fb77  ldc.i4.m1
0x1fb78  ble      loc_1FC00
0x1fb7d  ldarg.0
0x1fb7e  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fb83  ldloc.s  9
0x1fb85  callvirt instance valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DateOptions::fixYear(valuetype Microsoft.Reporting.WebForms.SimpleDate cDate)
0x1fb8a  stloc.s  9
0x1fb8c  ldarg.0
0x1fb8d  ldloc.s  9
0x1fb8f  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDayString(valuetype Microsoft.Reporting.WebForms.SimpleDate di)
0x1fb94  stloc.s  0xB
0x1fb96  ldarg.0
0x1fb97  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fb9c  ldloc.s  9
0x1fb9e  ldc.i4.6
0x1fb9f  callvirt instance valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DateOptions::AddDays(valuetype Microsoft.Reporting.WebForms.SimpleDate cDate, int32 nDays)
0x1fba4  stloc.s  0xA
0x1fba6  leave.s  loc_1FBAF
0x1fba8  pop
0x1fba9  ldloc.s  9
0x1fbab  stloc.s  0xA
0x1fbad  leave.s  loc_1FBAF
0x1fbaf  ldarg.0
0x1fbb0  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fbb5  callvirt instance valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.DateOptions::get_CalendarType()
0x1fbba  ldloc.s  0xA
0x1fbbc  ldarg.0
0x1fbbd  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fbc2  callvirt instance int32 Microsoft.Reporting.WebForms.DateOptions::get_FirstDayOfWeek()
0x1fbc7  ldarg.0
0x1fbc8  ldfld    int16 Microsoft.Reporting.WebForms.DatePicker::m_FirstWeekOfYear
0x1fbcd  call     int32 Microsoft.Reporting.WebForms.SPIntlCal::GetWeekNumber(valuetype Microsoft.Reporting.WebForms.SPCalendarType calType, valuetype Microsoft.Reporting.WebForms.SimpleDate di, int32 FirstDayOfWeek, int16 FirstWeekOfYear)
0x1fbd2  stloc.s  0xE
0x1fbd4  ldloc.s  0xE
0x1fbd6  ldc.i4.0
0x1fbd7  bgt.s    loc_1FC4E
0x1fbd9  ldarg.0
0x1fbda  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fbdf  callvirt instance valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.DateOptions::get_CalendarType()
0x1fbe4  ldloc.s  9
0x1fbe6  ldarg.0
0x1fbe7  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fbec  callvirt instance int32 Microsoft.Reporting.WebForms.DateOptions::get_FirstDayOfWeek()
0x1fbf1  ldarg.0
0x1fbf2  ldfld    int16 Microsoft.Reporting.WebForms.DatePicker::m_FirstWeekOfYear
0x1fbf7  call     int32 Microsoft.Reporting.WebForms.SPIntlCal::GetWeekNumber(valuetype Microsoft.Reporting.WebForms.SPCalendarType calType, valuetype Microsoft.Reporting.WebForms.SimpleDate di, int32 FirstDayOfWeek, int16 FirstWeekOfYear)
0x1fbfc  stloc.s  0xE
0x1fbfe  br.s     loc_1FC4E
0x1fc00  ldarg.2
0x1fc01  ldobj    Microsoft.Reporting.WebForms.SimpleDate
0x1fc06  stloc.s  0xA
0x1fc08  ldloca.s 0xA
0x1fc0a  ldc.i4.1
0x1fc0b  call     instance void Microsoft.Reporting.WebForms.SimpleDate::set_Day(int32 value)
0x1fc10  ldarg.0
0x1fc11  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fc16  ldloc.s  0xA
0x1fc18  callvirt instance valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DateOptions::fixYear(valuetype Microsoft.Reporting.WebForms.SimpleDate cDate)
0x1fc1d  stloc.s  0xA
0x1fc1f  ldarg.0
0x1fc20  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fc25  callvirt instance valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.DateOptions::get_CalendarType()
0x1fc2a  ldloc.s  0xA
0x1fc2c  ldarg.0
0x1fc2d  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fc32  callvirt instance int32 Microsoft.Reporting.WebForms.DateOptions::get_FirstDayOfWeek()
0x1fc37  ldarg.0
0x1fc38  ldfld    int16 Microsoft.Reporting.WebForms.DatePicker::m_FirstWeekOfYear
0x1fc3d  call     int32 Microsoft.Reporting.WebForms.SPIntlCal::GetWeekNumber(valuetype Microsoft.Reporting.WebForms.SPCalendarType calType, valuetype Microsoft.Reporting.WebForms.SimpleDate di, int32 FirstDayOfWeek, int16 FirstWeekOfYear)
0x1fc42  stloc.s  0xE
0x1fc44  ldarg.0
0x1fc45  ldloc.s  0xA
0x1fc47  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDayString(valuetype Microsoft.Reporting.WebForms.SimpleDate di)
0x1fc4c  stloc.s  0xB
0x1fc4e  ldarg.1
0x1fc4f  ldstr    aThScopeRowClas// "<th scope=\"row\" class={0} onmouseover"...
0x1fc54  ldloc.1
0x1fc55  brtrue.s loc_1FC79
0x1fc57  ldarg.0
0x1fc58  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bNeedDirections
0x1fc5d  brtrue.s loc_1FC67
0x1fc5f  ldarg.0
0x1fc60  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_cssClassWeek
0x1fc65  br.s     loc_1FC99
0x1fc67  ldarg.0
0x1fc68  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_cssClassWeek
0x1fc6d  ldstr    aRtl_0// "RTL"
0x1fc72  call     string [mscorlib]System.String::Concat(string, string)
0x1fc77  br.s     loc_1FC99
0x1fc79  ldarg.0
0x1fc7a  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bNeedDirections
0x1fc7f  brtrue.s loc_1FC89
0x1fc81  ldarg.0
0x1fc82  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_cssClassWeekSelected
0x1fc87  br.s     loc_1FC99
0x1fc89  ldarg.0
0x1fc8a  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_cssClassWeekSelected
0x1fc8f  ldstr    aRtl_0// "RTL"
0x1fc94  call     string [mscorlib]System.String::Concat(string, string)
0x1fc99  ldarg.0
0x1fc9a  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bNeedDirections
0x1fc9f  brtrue.s loc_1FCA9
0x1fca1  ldarg.0
0x1fca2  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_cssClassWeekSelected
0x1fca7  br.s     loc_1FCB9
0x1fca9  ldarg.0
0x1fcaa  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_cssClassWeekSelected
0x1fcaf  ldstr    aRtl_0// "RTL"
0x1fcb4  call     string [mscorlib]System.String::Concat(string, string)
0x1fcb9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fcbe  ldstr    aDivClass0AHref// "<div class={0}><a href=\"javascript:Mov"...
0x1fcc3  ldarg.0
0x1fcc4  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bNeedDirections
0x1fcc9  brtrue.s loc_1FCD3
0x1fccb  ldarg.0
0x1fccc  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_cssClassWeekBox
0x1fcd1  br.s     loc_1FCE3
0x1fcd3  ldarg.0
0x1fcd4  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_cssClassWeekBox
0x1fcd9  ldstr    aRtl_0// "RTL"
0x1fcde  call     string [mscorlib]System.String::Concat(string, string)
0x1fce3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fce8  ldstr    aAcronymTitle01// "<ACRONYM title=\"{0}\" >{1}</ACRONYM>"
0x1fced  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fcf2  ldarg.0
0x1fcf3  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_acronymstr
0x1fcf8  ldloc.s  0xE
0x1fcfa  box      [mscorlib]System.Int32
0x1fcff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x1fd04  ldloc.s  0xE
0x1fd06  box      [mscorlib]System.Int32
0x1fd0b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1fd10  ldloc.s  0xB
0x1fd12  call     string Microsoft.Reporting.WebForms.SPHttpUtility::EcmaScriptStringLiteralEncode(string scriptLiteralToEncode)
0x1fd17  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x1fd1c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x1fd21  pop
0x1fd22  ldc.i4.0
0x1fd23  stloc.s  0x10
0x1fd25  br       loc_1FF5F
0x1fd2a  ldarg.0
0x1fd2b  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fd30  ldloc.s  9
0x1fd32  callvirt instance valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DateOptions::fixYear(valuetype Microsoft.Reporting.WebForms.SimpleDate cDate)
0x1fd37  stloc.s  9
0x1fd39  ldloca.s 9
0x1fd3b  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Month()
0x1fd40  ldarg.2
0x1fd41  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Month()
0x1fd46  ceq
0x1fd48  stloc.s  0x11
0x1fd4a  ldarg.0
0x1fd4b  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.DatePicker::m_dopt
0x1fd50  ldloc.s  0x10
0x1fd52  callvirt instance bool Microsoft.Reporting.WebForms.DateOptions::IsWorkDay(int32 iDay)
0x1fd57  pop
0x1fd58  ldloca.s 9
0x1fd5a  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Year()
0x1fd5f  ldarg.0
0x1fd60  ldflda   valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DatePicker::m_SelectedDate
0x1fd65  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Year()
0x1fd6a  bne.un.s loc_1FD96
0x1fd6c  ldloca.s 9
0x1fd6e  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Month()
0x1fd73  ldarg.0
0x1fd74  ldflda   valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DatePicker::m_SelectedDate
0x1fd79  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Month()
0x1fd7e  bne.un.s loc_1FD96
0x1fd80  ldloca.s 9
0x1fd82  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Day()
0x1fd87  ldarg.0
0x1fd88  ldflda   valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DatePicker::m_SelectedDate
0x1fd8d  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Day()
0x1fd92  ceq
0x1fd94  br.s     loc_1FD97
0x1fd96  ldc.i4.0
  ... truncated ...
```
