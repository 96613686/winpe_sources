# Microsoft.Reporting.WebForms.DatePicker::RenderPickerHeaderAsHtml

- ea: `0x1f5d0`
- end: `0x1f97c`
- name: `Microsoft.Reporting.WebForms.DatePicker::RenderPickerHeaderAsHtml`
- size: `940`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1f3b0`

## callees

- `0x1f560`
- `0x1f5b0`
- `0x1f5d0`
- `0x1ffe0`
- `0x20100`
- `0x20120`
- `0x20140`
- `0x216b0`
- `0x219a0`

## string_xrefs

- `0x1f633`: `ShowLoading();MoveToDate('{0}', {1});`
- `0x1f7ee`: `ShowLoading();MoveToDate('{0}', {1});`

## pseudocode

```c

```

## disassembly

```asm
0x1f5d0  ldarg.0
0x1f5d1  ldfld    valuetype Microsoft.Reporting.WebForms.SimpleDate[] Microsoft.Reporting.WebForms.DatePicker::m_MonthInfo
0x1f5d6  ldarg.2
0x1f5d7  ldarg.0
0x1f5d8  ldfld    int32 Microsoft.Reporting.WebForms.DatePicker::m_StartMonthOffset
0x1f5dd  sub
0x1f5de  ldelem   Microsoft.Reporting.WebForms.SimpleDate
0x1f5e3  stloc.3
0x1f5e4  ldloca.s 3
0x1f5e6  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Year()
0x1f5eb  ldc.i4.m1
0x1f5ec  ble      loc_1F782
0x1f5f1  ldarg.0
0x1f5f2  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bShowNextPrevNavigation
0x1f5f7  brfalse  loc_1F782
0x1f5fc  ldarg.2
0x1f5fd  ldarg.0
0x1f5fe  ldfld    int32 Microsoft.Reporting.WebForms.DatePicker::m_StartMonthOffset
0x1f603  bne.un   loc_1F6A7
0x1f608  ldarg.0
0x1f609  ldflda   valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DatePicker::m_startMonth
0x1f60e  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Day()
0x1f613  ldloca.s 3
0x1f615  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Day()
0x1f61a  ble.s    loc_1F624
0x1f61c  ldloca.s 3
0x1f61e  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Day()
0x1f623  pop
0x1f624  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f629  ldstr    aTdAlignCenterA// " <td align=center><a id=\"{2}\" href=\""...
0x1f62e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f633  ldstr    aShowloadingMov// "ShowLoading();MoveToDate('{0}', {1});"
0x1f638  ldarg.0
0x1f639  ldloc.3
0x1f63a  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDayString(valuetype Microsoft.Reporting.WebForms.SimpleDate di)
0x1f63f  call     string Microsoft.Reporting.WebForms.SPHttpUtility::EcmaScriptStringLiteralEncode(string scriptLiteralToEncode)
0x1f644  ldstr    aTrue// "true"
0x1f649  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1f64e  ldarg.0
0x1f64f  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_prevNavText
0x1f654  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f659  brtrue.s loc_1F668
0x1f65b  ldarg.0
0x1f65c  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_prevNavText
0x1f661  call     string Microsoft.Reporting.WebForms.SPHttpUtility::HtmlEncode(string valueToEncode)
0x1f666  br.s     loc_1F694
0x1f668  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f66d  ldarg.0
0x1f66e  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_defaultPrevNavText
0x1f673  ldarg.0
0x1f674  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_backstr
0x1f679  ldarg.0
0x1f67a  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bNeedDirections
0x1f67f  brtrue.s loc_1F689
0x1f681  ldarg.0
0x1f682  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_backImage
0x1f687  br.s     loc_1F68F
0x1f689  ldarg.0
0x1f68a  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_forwardImage
0x1f68f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1f694  ldarg.0
0x1f695  ldarg.2
0x1f696  ldc.i4.1
0x1f697  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivFocusElement(int32 offset, bool previous)
0x1f69c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x1f6a1  stloc.0
0x1f6a2  br       loc_1F788
0x1f6a7  ldloca.s 3
0x1f6a9  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Year()
0x1f6ae  stloc.s  5
0x1f6b0  ldloca.s 5
0x1f6b2  ldstr    a0000// "0000"
0x1f6b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f6bc  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1f6c1  ldloca.s 3
0x1f6c3  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Month()
0x1f6c8  stloc.s  5
0x1f6ca  ldloca.s 5
0x1f6cc  ldstr    a00_0// "00"
0x1f6d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f6d6  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1f6db  ldstr    a01_2// "01"
0x1f6e0  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f6e5  stloc.2
0x1f6e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f6eb  ldstr    aTdAlignCenterA// " <td align=center><a id=\"{2}\" href=\""...
0x1f6f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f6f5  ldstr    aHideunhide0123// "HideUnhide('{0}','{1}','{2}', '{3}');"
0x1f6fa  ldc.i4.4
0x1f6fb  newarr   [mscorlib]System.Object
0x1f700  dup
0x1f701  ldc.i4.0
0x1f702  ldarg.0
0x1f703  ldarg.2
0x1f704  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivName(int32 offset)
0x1f709  stelem.ref
0x1f70a  dup
0x1f70b  ldc.i4.1
0x1f70c  ldarg.0
0x1f70d  ldarg.2
0x1f70e  ldc.i4.1
0x1f70f  sub
0x1f710  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivName(int32 offset)
0x1f715  stelem.ref
0x1f716  dup
0x1f717  ldc.i4.2
0x1f718  ldloc.2
0x1f719  stelem.ref
0x1f71a  dup
0x1f71b  ldc.i4.3
0x1f71c  ldarg.0
0x1f71d  ldarg.2
0x1f71e  ldc.i4.1
0x1f71f  sub
0x1f720  ldc.i4.1
0x1f721  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivFocusElement(int32 offset, bool previous)
0x1f726  stelem.ref
0x1f727  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f72c  ldarg.0
0x1f72d  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_prevNavText
0x1f732  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f737  brtrue.s loc_1F746
0x1f739  ldarg.0
0x1f73a  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_prevNavText
0x1f73f  call     string Microsoft.Reporting.WebForms.SPHttpUtility::HtmlEncode(string valueToEncode)
0x1f744  br.s     loc_1F772
0x1f746  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f74b  ldarg.0
0x1f74c  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_defaultPrevNavText
0x1f751  ldarg.0
0x1f752  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_backstr
0x1f757  ldarg.0
0x1f758  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bNeedDirections
0x1f75d  brtrue.s loc_1F767
0x1f75f  ldarg.0
0x1f760  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_backImage
0x1f765  br.s     loc_1F76D
0x1f767  ldarg.0
0x1f768  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_forwardImage
0x1f76d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1f772  ldarg.0
0x1f773  ldarg.2
0x1f774  ldc.i4.1
0x1f775  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivFocusElement(int32 offset, bool previous)
0x1f77a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x1f77f  stloc.0
0x1f780  br.s     loc_1F788
0x1f782  ldstr    aTdNbspTd// "<td>&nbsp;</td>"
0x1f787  stloc.0
0x1f788  ldarg.0
0x1f789  ldfld    valuetype Microsoft.Reporting.WebForms.SimpleDate[] Microsoft.Reporting.WebForms.DatePicker::m_MonthInfo
0x1f78e  ldarg.2
0x1f78f  ldarg.0
0x1f790  ldfld    int32 Microsoft.Reporting.WebForms.DatePicker::m_StartMonthOffset
0x1f795  sub
0x1f796  ldc.i4.2
0x1f797  add
0x1f798  ldelem   Microsoft.Reporting.WebForms.SimpleDate
0x1f79d  stloc.s  4
0x1f79f  ldloca.s 4
0x1f7a1  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Year()
0x1f7a6  ldc.i4.m1
0x1f7a7  ble      loc_1F93E
0x1f7ac  ldarg.0
0x1f7ad  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bShowNextPrevNavigation
0x1f7b2  brfalse  loc_1F93E
0x1f7b7  ldarg.2
0x1f7b8  ldarg.0
0x1f7b9  ldfld    int32 Microsoft.Reporting.WebForms.DatePicker::m_EndMonthOffset
0x1f7be  bne.un   loc_1F863
0x1f7c3  ldarg.0
0x1f7c4  ldflda   valuetype Microsoft.Reporting.WebForms.SimpleDate Microsoft.Reporting.WebForms.DatePicker::m_startMonth
0x1f7c9  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Day()
0x1f7ce  ldloca.s 4
0x1f7d0  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Day()
0x1f7d5  ble.s    loc_1F7DF
0x1f7d7  ldloca.s 4
0x1f7d9  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Day()
0x1f7de  pop
0x1f7df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f7e4  ldstr    aTdAlignCenterA// " <td align=center><a id=\"{2}\" href=\""...
0x1f7e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f7ee  ldstr    aShowloadingMov// "ShowLoading();MoveToDate('{0}', {1});"
0x1f7f3  ldarg.0
0x1f7f4  ldloc.s  4
0x1f7f6  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDayString(valuetype Microsoft.Reporting.WebForms.SimpleDate di)
0x1f7fb  call     string Microsoft.Reporting.WebForms.SPHttpUtility::EcmaScriptStringLiteralEncode(string scriptLiteralToEncode)
0x1f800  ldstr    aFalse// "false"
0x1f805  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1f80a  ldarg.0
0x1f80b  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_nextNavText
0x1f810  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f815  brtrue.s loc_1F824
0x1f817  ldarg.0
0x1f818  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_nextNavText
0x1f81d  call     string Microsoft.Reporting.WebForms.SPHttpUtility::HtmlEncode(string valueToEncode)
0x1f822  br.s     loc_1F850
0x1f824  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f829  ldarg.0
0x1f82a  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_defaultNextNavText
0x1f82f  ldarg.0
0x1f830  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_forwardstr
0x1f835  ldarg.0
0x1f836  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bNeedDirections
0x1f83b  brtrue.s loc_1F845
0x1f83d  ldarg.0
0x1f83e  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_forwardImage
0x1f843  br.s     loc_1F84B
0x1f845  ldarg.0
0x1f846  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_backImage
0x1f84b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1f850  ldarg.0
0x1f851  ldarg.2
0x1f852  ldc.i4.0
0x1f853  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivFocusElement(int32 offset, bool previous)
0x1f858  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x1f85d  stloc.1
0x1f85e  br       loc_1F944
0x1f863  ldloca.s 4
0x1f865  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Year()
0x1f86a  stloc.s  5
0x1f86c  ldloca.s 5
0x1f86e  ldstr    a0000// "0000"
0x1f873  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f878  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1f87d  ldloca.s 4
0x1f87f  call     instance int32 Microsoft.Reporting.WebForms.SimpleDate::get_Month()
0x1f884  stloc.s  5
0x1f886  ldloca.s 5
0x1f888  ldstr    a00_0// "00"
0x1f88d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f892  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1f897  ldstr    a01_2// "01"
0x1f89c  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f8a1  stloc.2
0x1f8a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f8a7  ldstr    aTdAlignCenterA// " <td align=center><a id=\"{2}\" href=\""...
0x1f8ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f8b1  ldstr    aHideunhide0123// "HideUnhide('{0}','{1}','{2}', '{3}');"
0x1f8b6  ldc.i4.4
0x1f8b7  newarr   [mscorlib]System.Object
0x1f8bc  dup
0x1f8bd  ldc.i4.0
0x1f8be  ldarg.0
0x1f8bf  ldarg.2
0x1f8c0  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivName(int32 offset)
0x1f8c5  stelem.ref
0x1f8c6  dup
0x1f8c7  ldc.i4.1
0x1f8c8  ldarg.0
0x1f8c9  ldarg.2
0x1f8ca  ldc.i4.1
0x1f8cb  add
0x1f8cc  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivName(int32 offset)
0x1f8d1  stelem.ref
0x1f8d2  dup
0x1f8d3  ldc.i4.2
0x1f8d4  ldloc.2
0x1f8d5  stelem.ref
0x1f8d6  dup
0x1f8d7  ldc.i4.3
0x1f8d8  ldarg.0
0x1f8d9  ldarg.2
0x1f8da  ldc.i4.1
0x1f8db  add
0x1f8dc  ldc.i4.0
0x1f8dd  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivFocusElement(int32 offset, bool previous)
0x1f8e2  stelem.ref
0x1f8e3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f8e8  ldarg.0
0x1f8e9  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_nextNavText
0x1f8ee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f8f3  brtrue.s loc_1F902
0x1f8f5  ldarg.0
0x1f8f6  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_nextNavText
0x1f8fb  call     string Microsoft.Reporting.WebForms.SPHttpUtility::HtmlEncode(string valueToEncode)
0x1f900  br.s     loc_1F92E
0x1f902  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f907  ldarg.0
0x1f908  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_defaultNextNavText
0x1f90d  ldarg.0
0x1f90e  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_forwardstr
0x1f913  ldarg.0
0x1f914  ldfld    bool Microsoft.Reporting.WebForms.DatePicker::m_bNeedDirections
0x1f919  brtrue.s loc_1F923
0x1f91b  ldarg.0
0x1f91c  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_forwardImage
0x1f921  br.s     loc_1F929
0x1f923  ldarg.0
0x1f924  ldfld    string Microsoft.Reporting.WebForms.DatePicker::m_backImage
0x1f929  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1f92e  ldarg.0
0x1f92f  ldarg.2
0x1f930  ldc.i4.0
0x1f931  call     instance string Microsoft.Reporting.WebForms.DatePicker::GetDivFocusElement(int32 offset, bool previous)
0x1f936  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x1f93b  stloc.1
0x1f93c  br.s     loc_1F944
0x1f93e  ldstr    aTdNbspTd// "<td>&nbsp;</td>"
0x1f943  stloc.1
  ... truncated ...
```
