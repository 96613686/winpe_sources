# Microsoft.ReportingServices.Diagnostics.Localization::SetCultureFromPriorityList_0

- ea: `0x3810`
- end: `0x38a2`
- name: `Microsoft.ReportingServices.Diagnostics.Localization::SetCultureFromPriorityList_0`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x3610`

## callees

- `0x3720`
- `0x3810`
- `0x3950`
- `0x39e0`
- `0x3ba0`

## pseudocode

```c

```

## disassembly

```asm
0x3810  ldarg.0
0x3811  brfalse.s loc_3828
0x3813  ldsfld   class [mscorlib]System.Threading.AsyncLocal`1<string> Microsoft.ReportingServices.Diagnostics.Localization::_clientCurrentNativeUICulture
0x3818  ldstr    asc_1B472// ","
0x381d  ldarg.0
0x381e  call     string [mscorlib]System.String::Join(string, string[])
0x3823  callvirt instance void class [mscorlib]System.Threading.AsyncLocal`1<string>::set_Value(var<u1>)
0x3828  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x382d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3832  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentCulture(class [mscorlib]System.Globalization.CultureInfo)
0x3837  ldc.i4.0
0x3838  stloc.0
0x3839  ldarg.0
0x383a  brfalse.s loc_388F
0x383c  ldarg.0
0x383d  stloc.1
0x383e  ldc.i4.0
0x383f  stloc.2
0x3840  br.s     loc_3889
0x3842  ldloc.1
0x3843  ldloc.2
0x3844  ldelem.ref
0x3845  call     string Microsoft.ReportingServices.Diagnostics.Localization::GetNormalizedLocale(string locale)
0x384a  stloc.3
0x384b  ldloc.0
0x384c  brtrue.s loc_3869
0x384e  ldloc.3
0x384f  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.Localization::GetCultureInfoNoUserOverrides(string cultureName)
0x3854  stloc.s  4
0x3856  ldsfld   class [mscorlib]System.Threading.AsyncLocal`1<class [mscorlib]System.Globalization.CultureInfo> Microsoft.ReportingServices.Diagnostics.Localization::_clientPrimaryCulture
0x385b  ldloc.s  4
0x385d  callvirt instance void class [mscorlib]System.Threading.AsyncLocal`1<class [mscorlib]System.Globalization.CultureInfo>::set_Value(var<u1>)
0x3862  ldc.i4.1
0x3863  stloc.0
0x3864  leave.s  loc_3869
0x3866  pop
0x3867  leave.s  loc_3869
0x3869  ldarg.1
0x386a  brfalse.s loc_3885
0x386c  ldloc.3
0x386d  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.Localization::InstalledCulture(string locale)
0x3872  stloc.s  5
0x3874  ldloc.s  5
0x3876  brfalse.s loc_3885
0x3878  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x387d  ldloc.s  5
0x387f  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentUICulture(class [mscorlib]System.Globalization.CultureInfo)
0x3884  ret
0x3885  ldloc.2
0x3886  ldc.i4.1
0x3887  add
0x3888  stloc.2
0x3889  ldloc.2
0x388a  ldloc.1
0x388b  ldlen
0x388c  conv.i4
0x388d  blt.s    loc_3842
0x388f  ldarg.1
0x3890  brfalse.s loc_38A1
0x3892  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x3897  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Diagnostics.Localization::get_FallbackUICulture()
0x389c  callvirt instance void [mscorlib]System.Threading.Thread::set_CurrentUICulture(class [mscorlib]System.Globalization.CultureInfo)
0x38a1  ret
```
