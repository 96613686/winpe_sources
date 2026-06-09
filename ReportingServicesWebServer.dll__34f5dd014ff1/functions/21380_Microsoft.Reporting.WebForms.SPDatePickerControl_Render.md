# Microsoft.Reporting.WebForms.SPDatePickerControl::Render

- ea: `0x21380`
- end: `0x214e3`
- name: `Microsoft.Reporting.WebForms.SPDatePickerControl::Render`
- size: `355`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x15e0`
- `0x40b0`
- `0x1c1e0`
- `0x1ef40`
- `0x1ef80`
- `0x1f170`
- `0x1f190`
- `0x1f260`
- `0x20f50`
- `0x20fa0`
- `0x21010`
- `0x21360`
- `0x21380`
- `0x21780`

## string_xrefs

- `0x2146b`: `<LINK REL="stylesheet" TYPE="text/css" HREF="`

## pseudocode

```c

```

## disassembly

```asm
0x21380  ldarg.0
0x21381  ldarg.0
0x21382  ldflda   int32 Microsoft.Reporting.WebForms.SPDatePickerControl::_lcid
0x21387  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2138c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x21391  ldarg.0
0x21392  ldfld    valuetype Microsoft.Reporting.WebForms.SPCalendarType Microsoft.Reporting.WebForms.SPDatePickerControl::_calendar
0x21397  ldarg.0
0x21398  ldfld    string Microsoft.Reporting.WebForms.SPDatePickerControl::_ww
0x2139d  ldarg.0
0x2139e  ldflda   int32 Microsoft.Reporting.WebForms.SPDatePickerControl::_fdow
0x213a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x213a8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x213ad  ldarg.0
0x213ae  ldflda   int32 Microsoft.Reporting.WebForms.SPDatePickerControl::_hj
0x213b3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x213b8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x213bd  ldarg.0
0x213be  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Reporting.WebForms.SPDatePickerControl::_timezone
0x213c3  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MinValue
0x213c8  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x213cd  brtrue.s loc_213D2
0x213cf  ldnull
0x213d0  br.s     loc_213E3
0x213d2  ldarg.0
0x213d3  ldflda   valuetype [mscorlib]System.TimeSpan Microsoft.Reporting.WebForms.SPDatePickerControl::_timezone
0x213d8  constrained. [mscorlib]System.TimeSpan
0x213de  callvirt instance string [mscorlib]System.Object::ToString()
0x213e3  ldarg.0
0x213e4  ldfld    int32 Microsoft.Reporting.WebForms.SPDatePickerControl::_tdym
0x213e9  ldc.i4.m1
0x213ea  beq.s    loc_213FE
0x213ec  ldarg.0
0x213ed  ldflda   int32 Microsoft.Reporting.WebForms.SPDatePickerControl::_tdym
0x213f2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x213f7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x213fc  br.s     loc_213FF
0x213fe  ldnull
0x213ff  ldarg.0
0x21400  call     instance string Microsoft.Reporting.WebForms.SPDatePickerControl::get_SelectedDate()
0x21405  ldarg.0
0x21406  call     instance string Microsoft.Reporting.WebForms.SPDatePickerControl::get_StartMonth()
0x2140b  newobj   instance void Microsoft.Reporting.WebForms.DateOptions::.ctor(string localeId, valuetype Microsoft.Reporting.WebForms.SPCalendarType calendar, string workWeek, string firstDayOfWeek, string hijriAdjustment, string timeZoneSpan, string twoDigitYearMax, string selectedDate, string startMonth)
0x21410  stfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.SPDatePickerControl::_dateOptions
0x21415  ldarg.0
0x21416  callvirt instance void Microsoft.Reporting.WebForms.SPDatePickerControl::InitDatePicker()
0x2141b  ldarg.0
0x2141c  ldfld    class Microsoft.Reporting.WebForms.DatePicker Microsoft.Reporting.WebForms.SPDatePickerControl::_datePicker
0x21421  ldarg.0
0x21422  ldfld    class Microsoft.Reporting.WebForms.DateOptions Microsoft.Reporting.WebForms.SPDatePickerControl::_dateOptions
0x21427  callvirt instance void Microsoft.Reporting.WebForms.DatePicker::set_DateTimeOptions(class Microsoft.Reporting.WebForms.DateOptions value)
0x2142c  ldarg.0
0x2142d  ldfld    class Microsoft.Reporting.WebForms.DatePicker Microsoft.Reporting.WebForms.SPDatePickerControl::_datePicker
0x21432  ldarg.0
0x21433  call     instance int32 Microsoft.Reporting.WebForms.SPDatePickerControl::get_LangId()
0x21438  callvirt instance void Microsoft.Reporting.WebForms.DatePicker::set_LangId(int32 value)
0x2143d  ldarg.1
0x2143e  ldstr    aDivClassMsRsCa// "<div class='ms-rs-calendar-loading' id="...
0x21443  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x21448  ldarg.1
0x21449  call     class Microsoft.Reporting.WebForms.IReportViewerMessages5 Microsoft.Reporting.WebForms.LocalizationHelper::get_Current()
0x2144e  callvirt instance string Microsoft.Reporting.WebForms.IReportViewerMessages3::get_CalendarLoading()
0x21453  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x21458  ldarg.1
0x21459  ldstr    aDiv// "</div>"
0x2145e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x21463  ldarg.0
0x21464  ldfld    string Microsoft.Reporting.WebForms.SPDatePickerControl::_urlCssClass
0x21469  brfalse.s loc_21492
0x2146b  ldstr    aLinkRelStylesh// "<LINK REL=\"stylesheet\" TYPE=\"text/cs"...
0x21470  ldarg.0
0x21471  ldfld    string Microsoft.Reporting.WebForms.SPDatePickerControl::_urlCssClass
0x21476  callvirt instance string [mscorlib]System.Object::ToString()
0x2147b  call     string Microsoft.Reporting.WebForms.SPHttpUtility::HtmlUrlAttributeEncode(string urlAttributeToEncode)
0x21480  ldstr    asc_4C3D0// "\">"
0x21485  call     string [mscorlib]System.String::Concat(string, string, string)
0x2148a  stloc.1
0x2148b  ldarg.1
0x2148c  ldloc.1
0x2148d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x21492  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x21497  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2149c  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x214a1  pop
0x214a2  ldarg.0
0x214a3  ldfld    class Microsoft.Reporting.WebForms.DatePicker Microsoft.Reporting.WebForms.SPDatePickerControl::_datePicker
0x214a8  ldarg.0
0x214a9  ldfld    string Microsoft.Reporting.WebForms.SPDatePickerControl::_imageDirName
0x214ae  callvirt instance void Microsoft.Reporting.WebForms.DatePicker::set_ImageDirName(string value)
0x214b3  ldarg.0
0x214b4  ldfld    class Microsoft.Reporting.WebForms.DatePicker Microsoft.Reporting.WebForms.SPDatePickerControl::_datePicker
0x214b9  ldarg.0
0x214ba  ldfld    int16 Microsoft.Reporting.WebForms.SPDatePickerControl::_firstWeekOfYear
0x214bf  callvirt instance void Microsoft.Reporting.WebForms.DatePicker::set_FirstWeekOfYear(int16 value)
0x214c4  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x214c9  stloc.0
0x214ca  ldarg.0
0x214cb  ldfld    class Microsoft.Reporting.WebForms.DatePicker Microsoft.Reporting.WebForms.SPDatePickerControl::_datePicker
0x214d0  ldloc.0
0x214d1  callvirt instance void Microsoft.Reporting.WebForms.DatePicker::RenderAsHtml(class [mscorlib]System.Text.StringBuilder st)
0x214d6  ldarg.1
0x214d7  ldloc.0
0x214d8  callvirt instance string [mscorlib]System.Object::ToString()
0x214dd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x214e2  ret
```
