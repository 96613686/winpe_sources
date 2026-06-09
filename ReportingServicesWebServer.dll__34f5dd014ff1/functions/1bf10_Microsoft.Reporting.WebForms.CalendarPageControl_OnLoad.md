# Microsoft.Reporting.WebForms.CalendarPageControl::OnLoad

- ea: `0x1bf10`
- end: `0x1c15f`
- name: `Microsoft.Reporting.WebForms.CalendarPageControl::OnLoad`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0xf2a0`
- `0x1beb0`
- `0x1bed0`
- `0x1bef0`
- `0x1bf10`
- `0x20f80`
- `0x20fd0`
- `0x21000`
- `0x212b0`

## string_xrefs

- `0x1bfa9`: `DatePickerDivMovePrevious`
- `0x1bfd0`: `DatePickerDivMoveNext`

## pseudocode

```c

```

## disassembly

```asm
0x1bf10  ldarg.0
0x1bf11  callvirt instance void [System.Web]System.Web.UI.Control::EnsureChildControls()
0x1bf16  ldarg.0
0x1bf17  call     instance string Microsoft.Reporting.WebForms.CalendarPageControl::get_CalendarScriptUrl()
0x1bf1c  brfalse.s loc_1BF2E
0x1bf1e  ldarg.0
0x1bf1f  call     instance string Microsoft.Reporting.WebForms.CalendarPageControl::get_CssUrl()
0x1bf24  brfalse.s loc_1BF2E
0x1bf26  ldarg.0
0x1bf27  call     instance string Microsoft.Reporting.WebForms.CalendarPageControl::get_ImageUrl()
0x1bf2c  brtrue.s loc_1BF39
0x1bf2e  ldstr    aMissingOneOfTh// "Missing one of the url properties"
0x1bf33  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1bf38  throw
0x1bf39  ldarg.0
0x1bf3a  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1bf3f  callvirt instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x1bf44  ldstr    aCalendarscript// "CalendarScriptInclude"
0x1bf49  ldarg.0
0x1bf4a  call     instance string Microsoft.Reporting.WebForms.CalendarPageControl::get_CalendarScriptUrl()
0x1bf4f  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptInclude(string, string)
0x1bf54  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1bf59  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1bf5e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1bf63  dup
0x1bf64  ldstr    aDate// "date"
0x1bf69  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::Get(string)
0x1bf6e  stloc.0
0x1bf6f  dup
0x1bf70  ldstr    aSelectdate_0// "selectDate"
0x1bf75  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::Get(string)
0x1bf7a  stloc.1
0x1bf7b  dup
0x1bf7c  ldstr    aLcid// "LCID"
0x1bf81  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::Get(string)
0x1bf86  stloc.2
0x1bf87  ldstr    aPrevious// "Previous"
0x1bf8c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::Get(string)
0x1bf91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1bf96  brtrue.s loc_1BFBF
0x1bf98  ldarg.0
0x1bf99  ldarg.0
0x1bf9a  ldfld    string Microsoft.Reporting.WebForms.CalendarPageControl::m_onPageLoadScript
0x1bf9f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bfa4  ldstr    aTryDocumentGet// "try{{document.getElementById('{0}').foc"...
0x1bfa9  ldstr    aDatepickerdivm// "DatePickerDivMovePrevious"
0x1bfae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x1bfb3  call     string [mscorlib]System.String::Concat(string, string)
0x1bfb8  stfld    string Microsoft.Reporting.WebForms.CalendarPageControl::m_onPageLoadScript
0x1bfbd  br.s     loc_1BFE4
0x1bfbf  ldarg.0
0x1bfc0  ldarg.0
0x1bfc1  ldfld    string Microsoft.Reporting.WebForms.CalendarPageControl::m_onPageLoadScript
0x1bfc6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bfcb  ldstr    aTryDocumentGet// "try{{document.getElementById('{0}').foc"...
0x1bfd0  ldstr    aDatepickerdivm_0// "DatePickerDivMoveNext"
0x1bfd5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x1bfda  call     string [mscorlib]System.String::Concat(string, string)
0x1bfdf  stfld    string Microsoft.Reporting.WebForms.CalendarPageControl::m_onPageLoadScript
0x1bfe4  ldloc.2
0x1bfe5  ldloca.s 3
0x1bfe7  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x1bfec  brfalse.s loc_1C01B
0x1bfee  ldarg.0
0x1bfef  ldfld    class Microsoft.Reporting.WebForms.SPDatePickerControl Microsoft.Reporting.WebForms.CalendarPageControl::m_calendar
0x1bff4  ldloc.3
0x1bff5  callvirt instance void Microsoft.Reporting.WebForms.SPDatePickerControl::set_LocaleId(int32 value)
0x1bffa  ldloc.3
0x1bffb  ldc.i4.0
0x1bffc  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32, bool)
0x1c001  stloc.s  6
0x1c003  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1c008  ldloc.s  6
0x1c00a  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x1c00f  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x1c014  ldloc.s  6
0x1c016  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentUICulture(class [mscorlib]System.Globalization.CultureInfo)
0x1c01b  ldloc.0
0x1c01c  brfalse.s loc_1C02B
0x1c01e  ldloc.0
0x1c01f  ldsfld   string [mscorlib]System.String::Empty
0x1c024  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c029  brfalse.s loc_1C02D
0x1c02b  ldloc.1
0x1c02c  stloc.0
0x1c02d  ldstr    asc_4064A// ""
0x1c032  stloc.s  4
0x1c034  ldloc.0
0x1c035  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c03a  brtrue.s loc_1C0BA
0x1c03c  ldloc.0
0x1c03d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1c042  ldloca.s 7
0x1c044  ldloca.s 8
0x1c046  call     bool Microsoft.Reporting.WebForms.JaimeToReplaceWithProcCore::TryParseDateTime(string strDateTime, class [mscorlib]System.Globalization.CultureInfo formatProvider, [out] valuetype [mscorlib]System.DateTimeOffset& dateTimeOffset, [out] bool& hasTimeOffset)
0x1c04b  brfalse.s loc_1C0BA
0x1c04d  ldarg.0
0x1c04e  ldfld    class Microsoft.Reporting.WebForms.SPDatePickerControl Microsoft.Reporting.WebForms.CalendarPageControl::m_calendar
0x1c053  ldloca.s 7
0x1c055  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_Date()
0x1c05a  stloc.s  9
0x1c05c  ldloca.s 9
0x1c05e  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0x1c063  callvirt instance void Microsoft.Reporting.WebForms.SPDatePickerControl::set_StartMonth(string value)
0x1c068  ldloc.s  8
0x1c06a  brtrue.s loc_1C07F
0x1c06c  ldloca.s 7
0x1c06e  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTimeOffset::get_TimeOfDay()
0x1c073  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Reporting.WebForms.CalendarPageControl::_Midnight
0x1c078  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1c07d  brfalse.s loc_1C097
0x1c07f  ldloca.s 7
0x1c081  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTimeOffset::get_TimeOfDay()
0x1c086  stloc.s  0xA
0x1c088  ldloca.s 0xA
0x1c08a  constrained. [mscorlib]System.TimeSpan
0x1c090  callvirt instance string [mscorlib]System.Object::ToString()
0x1c095  stloc.s  4
0x1c097  ldloc.s  8
0x1c099  brfalse.s loc_1C0BA
0x1c09b  ldloc.s  4
0x1c09d  ldstr    asc_42244// " "
0x1c0a2  ldloca.s 7
0x1c0a4  ldstr    aZzz_0// "zzz"
0x1c0a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1c0ae  call     instance string [mscorlib]System.DateTimeOffset::ToString(string, class [mscorlib]System.IFormatProvider)
0x1c0b3  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c0b8  stloc.s  4
0x1c0ba  ldstr    aVarTimeportion// "var timePortion = "
0x1c0bf  stloc.s  5
0x1c0c1  ldloc.s  4
0x1c0c3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c0c8  brfalse.s loc_1C0DA
0x1c0ca  ldloc.s  5
0x1c0cc  ldstr    aNull_0// "null;"
0x1c0d1  call     string [mscorlib]System.String::Concat(string, string)
0x1c0d6  stloc.s  5
0x1c0d8  br.s     loc_1C0EF
0x1c0da  ldloc.s  5
0x1c0dc  ldstr    asc_4B0A6// "' "
0x1c0e1  ldloc.s  4
0x1c0e3  ldstr    asc_4B0AC// "';"
0x1c0e8  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x1c0ed  stloc.s  5
0x1c0ef  ldarg.0
0x1c0f0  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1c0f5  callvirt instance class [System.Web]System.Web.UI.ClientScriptManager [System.Web]System.Web.UI.Page::get_ClientScript()
0x1c0fa  ldtoken  Microsoft.Reporting.WebForms.CalendarPageControl
0x1c0ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c104  ldstr    aTime// "time"
0x1c109  ldloc.s  5
0x1c10b  ldc.i4.1
0x1c10c  callvirt instance void [System.Web]System.Web.UI.ClientScriptManager::RegisterClientScriptBlock(class [mscorlib]System.Type, string, string, bool)
0x1c111  ldloc.1
0x1c112  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c117  brtrue.s loc_1C135
0x1c119  ldloc.1
0x1c11a  ldloca.s 0xB
0x1c11c  call     bool [mscorlib]System.DateTime::TryParse(string, valuetype [mscorlib]System.DateTime&)
0x1c121  brfalse.s loc_1C135
0x1c123  ldarg.0
0x1c124  ldfld    class Microsoft.Reporting.WebForms.SPDatePickerControl Microsoft.Reporting.WebForms.CalendarPageControl::m_calendar
0x1c129  ldloca.s 0xB
0x1c12b  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0x1c130  callvirt instance void Microsoft.Reporting.WebForms.SPDatePickerControl::set_SelectedDate(string value)
0x1c135  ldarg.0
0x1c136  ldfld    class Microsoft.Reporting.WebForms.SPDatePickerControl Microsoft.Reporting.WebForms.CalendarPageControl::m_calendar
0x1c13b  ldarg.0
0x1c13c  call     instance string Microsoft.Reporting.WebForms.CalendarPageControl::get_CssUrl()
0x1c141  stfld    string Microsoft.Reporting.WebForms.SPDatePickerControl::_urlCssClass
0x1c146  ldarg.0
0x1c147  ldfld    class Microsoft.Reporting.WebForms.SPDatePickerControl Microsoft.Reporting.WebForms.CalendarPageControl::m_calendar
0x1c14c  ldarg.0
0x1c14d  call     instance string Microsoft.Reporting.WebForms.CalendarPageControl::get_ImageUrl()
0x1c152  callvirt instance void Microsoft.Reporting.WebForms.SPDatePickerControl::set_ImageUrl(string value)
0x1c157  ldarg.0
0x1c158  ldarg.1
0x1c159  call     instance void [System.Web]System.Web.UI.Control::OnLoad(class [mscorlib]System.EventArgs)
0x1c15e  ret
```
