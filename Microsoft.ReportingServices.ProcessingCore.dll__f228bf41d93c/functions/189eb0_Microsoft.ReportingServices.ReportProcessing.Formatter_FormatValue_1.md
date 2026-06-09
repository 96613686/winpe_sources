# Microsoft.ReportingServices.ReportProcessing.Formatter::FormatValue_1

- ea: `0x189eb0`
- end: `0x18a203`
- name: `Microsoft.ReportingServices.ReportProcessing.Formatter::FormatValue_1`
- size: `851`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d430`
- `0x189ea0`

## callees

- `0x15e0`
- `0x133620`
- `0x133670`
- `0x1767c0`
- `0x17a400`
- `0x17bb50`
- `0x189eb0`
- `0x18a240`
- `0x18a2f0`
- `0x1fb640`

## string_xrefs

- `0x18a0cd`: `(!System.Threading.Thread.CurrentThread.CurrentCulture.DateTimeFormat.IsReadOnly)`

## pseudocode

```c

```

## disassembly

```asm
0x189eb0  ldnull
0x189eb1  stloc.0
0x189eb2  ldnull
0x189eb3  stloc.1
0x189eb4  ldc.i4.0
0x189eb5  stloc.2
0x189eb6  ldc.i4.0
0x189eb7  stloc.3
0x189eb8  ldc.i4.0
0x189eb9  stloc.s  4
0x189ebb  ldc.i4.0
0x189ebc  stloc.s  5
0x189ebe  ldc.i4.0
0x189ebf  stloc.s  6
0x189ec1  ldnull
0x189ec2  stloc.s  7
0x189ec4  ldnull
0x189ec5  stloc.s  8
0x189ec7  ldc.i4.0
0x189ec8  stloc.s  9
0x189eca  ldarg.0
0x189ecb  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportProcessing.Formatter::m_styleClass
0x189ed0  brfalse  loc_189F62
0x189ed5  ldarg.2
0x189ed6  brtrue.s loc_189F03
0x189ed8  ldarg.0
0x189ed9  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportProcessing.Formatter::m_styleClass
0x189ede  ldarg.0
0x189edf  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectType
0x189ee4  ldarg.0
0x189ee5  ldfld    string Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectName
0x189eea  ldstr    aFormat// "Format"
0x189eef  ldarg.0
0x189ef0  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.Formatter::m_context
0x189ef5  ldarg.0
0x189ef6  ldflda   bool Microsoft.ReportingServices.ReportProcessing.Formatter::m_sharedFormatSettings
0x189efb  ldarga.s 2
0x189efd  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.Style::GetStyleAttribute(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string styleAttributeName, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext context, bool& sharedFormatSettings, [out] string& styleStringValue)
0x189f02  pop
0x189f03  ldarg.0
0x189f04  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportProcessing.Formatter::m_styleClass
0x189f09  ldarg.0
0x189f0a  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectType
0x189f0f  ldarg.0
0x189f10  ldfld    string Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectName
0x189f15  ldstr    aLanguage// "Language"
0x189f1a  ldarg.0
0x189f1b  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.Formatter::m_context
0x189f20  ldarg.0
0x189f21  ldflda   bool Microsoft.ReportingServices.ReportProcessing.Formatter::m_sharedFormatSettings
0x189f26  ldloca.s 1
0x189f28  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.Style::GetStyleAttribute(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string styleAttributeName, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext context, bool& sharedFormatSettings, [out] string& styleStringValue)
0x189f2d  stloc.s  5
0x189f2f  ldarg.0
0x189f30  ldloc.1
0x189f31  ldloca.s 0
0x189f33  ldloca.s 3
0x189f35  ldloca.s 5
0x189f37  call     instance bool Microsoft.ReportingServices.ReportProcessing.Formatter::GetCulture(string language, class [mscorlib]System.Globalization.CultureInfo& formattingCulture, bool& isThreadCulture, int32& languageState)
0x189f3c  brtrue.s loc_189F48
0x189f3e  call     string RPRes::get_rsExpressionErrorValue()
0x189f43  stloc.s  7
0x189f45  ldc.i4.1
0x189f46  stloc.s  9
0x189f48  ldloc.s  9
0x189f4a  brtrue.s loc_189F62
0x189f4c  ldarg.3
0x189f4d  ldc.i4.s 0x10
0x189f4f  bne.un.s loc_189F62
0x189f51  ldarg.0
0x189f52  ldfld    bool Microsoft.ReportingServices.ReportProcessing.Formatter::m_calendarValidated
0x189f57  brtrue.s loc_189F62
0x189f59  ldarg.0
0x189f5a  ldloc.s  5
0x189f5c  ldloc.0
0x189f5d  call     instance void Microsoft.ReportingServices.ReportProcessing.Formatter::CreateAndValidateCalendar(int32 languageState, class [mscorlib]System.Globalization.CultureInfo formattingCulture)
0x189f62  ldloc.s  9
0x189f64  brtrue.s loc_189FB0
0x189f66  ldloc.0
0x189f67  brfalse.s loc_189FB0
0x189f69  ldarg.0
0x189f6a  ldfld    class [mscorlib]System.Globalization.Calendar Microsoft.ReportingServices.ReportProcessing.Formatter::m_formattingCalendar
0x189f6f  brfalse.s loc_189FB0
0x189f71  ldloc.3
0x189f72  brfalse.s loc_189F9F
0x189f74  ldloc.0
0x189f75  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x189f7a  callvirt instance bool [mscorlib]System.Globalization.DateTimeFormatInfo::get_IsReadOnly()
0x189f7f  brfalse.s loc_189F92
0x189f81  ldloc.0
0x189f82  callvirt instance object [mscorlib]System.Globalization.CultureInfo::Clone()
0x189f87  castclass [mscorlib]System.Globalization.CultureInfo
0x189f8c  stloc.0
0x189f8d  ldc.i4.1
0x189f8e  stloc.s  4
0x189f90  br.s     loc_189F9F
0x189f92  ldloc.0
0x189f93  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x189f98  callvirt instance class [mscorlib]System.Globalization.Calendar [mscorlib]System.Globalization.DateTimeFormatInfo::get_Calendar()
0x189f9d  stloc.s  8
0x189f9f  ldloc.0
0x189fa0  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x189fa5  ldarg.0
0x189fa6  ldfld    class [mscorlib]System.Globalization.Calendar Microsoft.ReportingServices.ReportProcessing.Formatter::m_formattingCalendar
0x189fab  callvirt instance void [mscorlib]System.Globalization.DateTimeFormatInfo::set_Calendar(class [mscorlib]System.Globalization.Calendar)
0x189fb0  ldloc.s  9
0x189fb2  brtrue   loc_18A058
0x189fb7  ldarg.2
0x189fb8  brfalse  loc_18A058
0x189fbd  ldarg.1
0x189fbe  isinst   [mscorlib]System.IFormattable
0x189fc3  brfalse  loc_18A058
0x189fc8  ldloc.0
0x189fc9  brtrue.s loc_189FD8
0x189fcb  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x189fd0  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x189fd5  stloc.0
0x189fd6  ldc.i4.1
0x189fd7  stloc.3
0x189fd8  ldarg.2
0x189fd9  ldstr    aX// "x"
0x189fde  ldc.i4.1
0x189fdf  call     int32 Microsoft.ReportingServices.ReportProcessing.ReportProcessing::CompareWithInvariantCulture(string x, string y, bool ignoreCase)
0x189fe4  brtrue.s loc_189FE9
0x189fe6  ldc.i4.1
0x189fe7  stloc.s  6
0x189fe9  ldarg.1
0x189fea  castclass [mscorlib]System.IFormattable
0x189fef  ldarg.2
0x189ff0  ldloc.0
0x189ff1  callvirt instance string [mscorlib]System.IFormattable::ToString(string, class [mscorlib]System.IFormatProvider)
0x189ff6  stloc.s  7
0x189ff8  ldarg.s  4
0x189ffa  brfalse.s loc_18A010
0x189ffc  ldloc.s  7
0x189ffe  ldstr    a0_3// " +0"
0x18a003  ldloc.0
0x18a004  call     instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x18a009  call     string [mscorlib]System.String::Concat(string, string)
0x18a00e  stloc.s  7
0x18a010  leave.s  loc_18A055
0x18a012  stloc.s  0xA
0x18a014  call     string RPRes::get_rsExpressionErrorValue()
0x18a019  stloc.s  7
0x18a01b  ldarg.0
0x18a01c  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.Formatter::m_context
0x18a021  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ErrorContext Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext::get_ErrorContext()
0x18a026  ldc.i4   0x183
0x18a02b  ldc.i4.1
0x18a02c  ldarg.0
0x18a02d  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectType
0x18a032  ldarg.0
0x18a033  ldfld    string Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectName
0x18a038  ldstr    aFormat// "Format"
0x18a03d  ldc.i4.1
0x18a03e  newarr   [mscorlib]System.String
0x18a043  dup
0x18a044  ldc.i4.0
0x18a045  ldloc.s  0xA
0x18a047  callvirt instance string [mscorlib]System.Exception::get_Message()
0x18a04c  stelem.ref
0x18a04d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x18a052  pop
0x18a053  leave.s  loc_18A055
0x18a055  ldc.i4.1
0x18a056  stloc.s  9
0x18a058  ldloc.s  9
0x18a05a  brtrue.s loc_18A0A8
0x18a05c  ldnull
0x18a05d  stloc.s  0xB
0x18a05f  ldloc.3
0x18a060  brtrue.s loc_18A068
0x18a062  ldloc.0
0x18a063  ldnull
0x18a064  cgt.un
0x18a066  br.s     loc_18A069
0x18a068  ldc.i4.0
0x18a069  ldloc.s  4
0x18a06b  or
0x18a06c  brfalse.s loc_18A0A0
0x18a06e  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x18a073  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x18a078  stloc.s  0xB
0x18a07a  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x18a07f  ldloc.0
0x18a080  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x18a085  ldarg.1
0x18a086  callvirt instance string [mscorlib]System.Object::ToString()
0x18a08b  stloc.s  7
0x18a08d  leave.s  loc_18A0EE
0x18a08f  ldloc.s  0xB
0x18a091  brfalse.s loc_18A09F
0x18a093  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x18a098  ldloc.s  0xB
0x18a09a  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x18a09f  endfinally
0x18a0a0  ldarg.1
0x18a0a1  callvirt instance string [mscorlib]System.Object::ToString()
0x18a0a6  stloc.s  7
0x18a0a8  leave.s  loc_18A0EE
0x18a0aa  ldloc.3
0x18a0ab  brfalse.s loc_18A0ED
0x18a0ad  ldloc.s  8
0x18a0af  brfalse.s loc_18A0ED
0x18a0b1  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x18a0b6  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x18a0bb  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x18a0c0  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x18a0c5  callvirt instance bool [mscorlib]System.Globalization.DateTimeFormatInfo::get_IsReadOnly()
0x18a0ca  ldc.i4.0
0x18a0cb  ceq
0x18a0cd  ldstr    aSystemThreadin// "(!System.Threading.Thread.CurrentThread"...
0x18a0d2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x18a0d7  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x18a0dc  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x18a0e1  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x18a0e6  ldloc.s  8
0x18a0e8  callvirt instance void [mscorlib]System.Globalization.DateTimeFormatInfo::set_Calendar(class [mscorlib]System.Globalization.Calendar)
0x18a0ed  endfinally
0x18a0ee  ldloc.s  6
0x18a0f0  brtrue   loc_18A200
0x18a0f5  ldarg.0
0x18a0f6  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportProcessing.Formatter::m_styleClass
0x18a0fb  brfalse  loc_18A200
0x18a100  ldarg.3
0x18a101  ldc.i4.5
0x18a102  sub
0x18a103  ldc.i4.s 0xA
0x18a105  bgt.un.s loc_18A109
0x18a107  ldc.i4.1
0x18a108  stloc.2
0x18a109  ldloc.2
0x18a10a  brfalse  loc_18A200
0x18a10f  ldc.i4.1
0x18a110  stloc.s  0xC
0x18a112  ldarg.0
0x18a113  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportProcessing.Formatter::m_styleClass
0x18a118  ldarg.0
0x18a119  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectType
0x18a11e  ldarg.0
0x18a11f  ldfld    string Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectName
0x18a124  ldstr    aNumeralvariant// "NumeralVariant"
0x18a129  ldarg.0
0x18a12a  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.Formatter::m_context
0x18a12f  ldarg.0
0x18a130  ldflda   bool Microsoft.ReportingServices.ReportProcessing.Formatter::m_sharedFormatSettings
0x18a135  ldloca.s 0xC
0x18a137  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.Style::GetStyleAttribute(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string styleAttributeName, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext context, bool& sharedFormatSettings, [out] int32& styleIntValue)
0x18a13c  ldloc.s  0xC
0x18a13e  ldc.i4.2
0x18a13f  ble      loc_18A200
0x18a144  ldloc.0
0x18a145  stloc.s  0xD
0x18a147  ldloc.s  0xD
0x18a149  brtrue.s loc_18A157
0x18a14b  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x18a150  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentCulture()
0x18a155  stloc.s  0xD
0x18a157  ldloc.s  0xD
0x18a159  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0x18a15e  callvirt instance string [mscorlib]System.Globalization.NumberFormatInfo::get_NumberDecimalSeparator()
0x18a163  stloc.s  0xE
0x18a165  ldarg.0
0x18a166  ldfld    class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportProcessing.Formatter::m_styleClass
0x18a16b  ldarg.0
0x18a16c  ldfld    valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectType
0x18a171  ldarg.0
0x18a172  ldfld    string Microsoft.ReportingServices.ReportProcessing.Formatter::m_objectName
0x18a177  ldstr    aNumerallanguag// "NumeralLanguage"
0x18a17c  ldarg.0
0x18a17d  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.Formatter::m_context
0x18a182  ldarg.0
0x18a183  ldflda   bool Microsoft.ReportingServices.ReportProcessing.Formatter::m_sharedFormatSettings
0x18a188  ldloca.s 1
0x18a18a  callvirt instance int32 Microsoft.ReportingServices.ReportIntermediateFormat.Style::GetStyleAttribute(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string styleAttributeName, class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext context, bool& sharedFormatSettings, [out] string& styleStringValue)
0x18a18f  pop
0x18a190  ldloc.1
0x18a191  brfalse.s loc_18A19D
0x18a193  ldloc.1
0x18a194  ldc.i4.0
0x18a195  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(string, bool)
0x18a19a  stloc.0
0x18a19b  br.s     loc_18A1A3
0x18a19d  ldloc.0
0x18a19e  brtrue.s loc_18A1A3
0x18a1a0  ldloc.s  0xD
0x18a1a2  stloc.0
0x18a1a3  ldc.i4.1
0x18a1a4  stloc.s  0xF
0x18a1a6  ldloc.s  7
0x18a1a8  ldloc.s  0xC
0x18a1aa  ldloc.0
0x18a1ab  ldloc.s  0xE
0x18a1ad  ldloca.s 0xF
0x18a1af  call     string Microsoft.ReportingServices.ReportProcessing.FormatDigitReplacement::FormatNumeralVariant(string number, int32 numeralVariant, class [mscorlib]System.Globalization.CultureInfo numeralLanguage, string numberDecimalSeparator, [out] bool& numberTranslated)
0x18a1b4  stloc.s  7
0x18a1b6  ldloc.s  0xF
0x18a1b8  brtrue.s loc_18A200
0x18a1ba  ldarg.0
0x18a1bb  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.OnDemandProcessingContext Microsoft.ReportingServices.ReportProcessing.Formatter::m_context
  ... truncated ...
```
