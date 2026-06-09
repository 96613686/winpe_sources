# Microsoft.ReportingServices.Diagnostics.RSConfiguration::GetReportServerUrl

- ea: `0x6700`
- end: `0x69fe`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::GetReportServerUrl`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x65e0`

## callees

- `0x3450`
- `0x3640`
- `0x3fd0`
- `0x3fe0`
- `0x3ff0`
- `0x4130`
- `0x6170`
- `0x6700`

## string_xrefs

- `0x674b`: `Failed to get url configuration section.`
- `0x67e9`: `Invalid Report Server URL in configuration: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6700  ldarg.2
0x6701  ldnull
0x6702  stind.ref
0x6703  ldarg.1
0x6704  brtrue.s loc_670E
0x6706  ldarg.0
0x6707  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ReportServerExternalUrl()
0x670c  br.s     loc_6714
0x670e  ldarg.0
0x670f  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ReportServerUrl()
0x6714  stloc.0
0x6715  ldloc.0
0x6716  brfalse.s loc_6731
0x6718  ldnull
0x6719  stloc.s  0xD
0x671b  ldloc.0
0x671c  ldc.i4.0
0x671d  ldloca.s 0xD
0x671f  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x6724  brfalse.s loc_672F
0x6726  ldarg.2
0x6727  ldloc.s  0xD
0x6729  callvirt instance string [System]System.Uri::get_Host()
0x672e  stind.ref
0x672f  ldloc.0
0x6730  ret
0x6731  ldarg.0
0x6732  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration> Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_UrlConfiguration()
0x6737  brtrue.s loc_6757
0x6739  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x673e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x6743  brfalse.s loc_6755
0x6745  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x674a  ldc.i4.1
0x674b  ldstr    aFailedToGetUrl// "Failed to get url configuration section"...
0x6750  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6755  ldnull
0x6756  ret
0x6757  ldarg.0
0x6758  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration> Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_UrlConfiguration()
0x675d  ldc.i4.1
0x675e  ldloca.s 1
0x6760  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::TryGetValue(var<u1>, !!T0)
0x6765  brtrue.s loc_6785
0x6767  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x676c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x6771  brfalse.s loc_6783
0x6773  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6778  ldc.i4.1
0x6779  ldstr    aFailedToGetRep// "Failed to get report server url reserva"...
0x677e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6783  ldnull
0x6784  ret
0x6785  ldnull
0x6786  stloc.2
0x6787  ldnull
0x6788  stloc.3
0x6789  ldnull
0x678a  stloc.s  4
0x678c  ldnull
0x678d  stloc.s  5
0x678f  ldnull
0x6790  stloc.s  6
0x6792  ldnull
0x6793  stloc.s  7
0x6795  ldnull
0x6796  stloc.s  8
0x6798  ldnull
0x6799  stloc.s  9
0x679b  ldnull
0x679c  stloc.s  0xA
0x679e  ldnull
0x679f  stloc.s  0xB
0x67a1  ldloc.1
0x67a2  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation[] Microsoft.ReportingServices.Diagnostics.UrlConfiguration::UrlReservations
0x67a7  stloc.s  0xE
0x67a9  ldc.i4.0
0x67aa  stloc.s  0xF
0x67ac  br       loc_68F3
0x67b1  ldloc.s  0xE
0x67b3  ldloc.s  0xF
0x67b5  ldelem   Microsoft.ReportingServices.Diagnostics.UrlReservation
0x67ba  stloc.s  0x10
0x67bc  ldloc.s  0x10
0x67be  ldfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x67c3  ldloca.s 0x12
0x67c5  ldloca.s 0x11
0x67c7  ldloca.s 0x15
0x67c9  ldloca.s 0x13
0x67cb  ldloca.s 0x14
0x67cd  call     bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::ParseUrlPrefix(string url, [out] string& scheme, [out] string& host, [out] string& port, [out] string& prefix, [out] string& path)
0x67d2  brtrue.s loc_6808
0x67d4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x67d9  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x67de  brfalse  loc_68ED
0x67e3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x67e8  ldc.i4.2
0x67e9  ldstr    aInvalidReportS// "Invalid Report Server URL in configurat"...
0x67ee  ldc.i4.1
0x67ef  newarr   [mscorlib]System.Object
0x67f4  dup
0x67f5  ldc.i4.0
0x67f6  ldloc.s  0x10
0x67f8  ldfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x67fd  stelem.ref
0x67fe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6803  br       loc_68ED
0x6808  ldloc.s  0x12
0x680a  ldsfld   string [System]System.Uri::UriSchemeHttps
0x680f  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6814  ldc.i4.0
0x6815  ceq
0x6817  stloc.s  0x17
0x6819  ldloc.s  0x11
0x681b  ldstr    asc_14878// "*"
0x6820  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6825  brfalse.s loc_6835
0x6827  ldloc.s  0x11
0x6829  ldstr    asc_1487C// "+"
0x682e  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6833  brtrue.s loc_6890
0x6835  ldnull
0x6836  stloc.s  0x18
0x6838  ldarg.0
0x6839  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_Hostname()
0x683e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6843  brtrue.s loc_685B
0x6845  ldarg.0
0x6846  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_Hostname()
0x684b  ldstr    asc_14880// ":"
0x6850  ldloc.s  0x15
0x6852  call     string [mscorlib]System.String::Concat(string, string, string)
0x6857  stloc.s  0x18
0x6859  br.s     loc_6878
0x685b  ldarg.1
0x685c  brtrue.s loc_6865
0x685e  call     string [mscorlib]System.Environment::get_MachineName()
0x6863  br.s     loc_686A
0x6865  ldstr    aLocalhost// "localhost"
0x686a  ldstr    asc_14880// ":"
0x686f  ldloc.s  0x15
0x6871  call     string [mscorlib]System.String::Concat(string, string, string)
0x6876  stloc.s  0x18
0x6878  ldloc.s  0x17
0x687a  brfalse.s loc_6886
0x687c  ldloc.s  9
0x687e  brtrue.s loc_68ED
0x6880  ldloc.s  0x18
0x6882  stloc.s  9
0x6884  br.s     loc_68ED
0x6886  ldloc.s  6
0x6888  brtrue.s loc_68ED
0x688a  ldloc.s  0x18
0x688c  stloc.s  6
0x688e  br.s     loc_68ED
0x6890  ldloc.s  0x11
0x6892  ldloca.s 0x16
0x6894  call     bool [System]System.Net.IPAddress::TryParse(string, class [System]System.Net.IPAddress&)
0x6899  brfalse.s loc_68C3
0x689b  ldloc.s  0x11
0x689d  ldstr    asc_14880// ":"
0x68a2  ldloc.s  0x15
0x68a4  call     string [mscorlib]System.String::Concat(string, string, string)
0x68a9  stloc.s  0x19
0x68ab  ldloc.s  0x17
0x68ad  brfalse.s loc_68B9
0x68af  ldloc.s  0xA
0x68b1  brtrue.s loc_68ED
0x68b3  ldloc.s  0x19
0x68b5  stloc.s  0xA
0x68b7  br.s     loc_68ED
0x68b9  ldloc.s  7
0x68bb  brtrue.s loc_68ED
0x68bd  ldloc.s  0x19
0x68bf  stloc.s  7
0x68c1  br.s     loc_68ED
0x68c3  ldloc.s  8
0x68c5  brtrue.s loc_68ED
0x68c7  ldloc.s  0x11
0x68c9  ldstr    asc_14880// ":"
0x68ce  ldloc.s  0x15
0x68d0  call     string [mscorlib]System.String::Concat(string, string, string)
0x68d5  stloc.s  0x1A
0x68d7  ldloc.s  0x17
0x68d9  brfalse.s loc_68E5
0x68db  ldloc.s  0xB
0x68dd  brtrue.s loc_68ED
0x68df  ldloc.s  0x1A
0x68e1  stloc.s  0xB
0x68e3  br.s     loc_68ED
0x68e5  ldloc.s  8
0x68e7  brtrue.s loc_68ED
0x68e9  ldloc.s  0x1A
0x68eb  stloc.s  8
0x68ed  ldloc.s  0xF
0x68ef  ldc.i4.1
0x68f0  add
0x68f1  stloc.s  0xF
0x68f3  ldloc.s  0xF
0x68f5  ldloc.s  0xE
0x68f7  ldlen
0x68f8  conv.i4
0x68f9  blt      loc_67B1
0x68fe  ldloc.s  9
0x6900  brfalse.s loc_6908
0x6902  ldloc.s  9
0x6904  stloc.s  5
0x6906  br.s     loc_691A
0x6908  ldloc.s  0xA
0x690a  brfalse.s loc_6912
0x690c  ldloc.s  0xA
0x690e  stloc.s  5
0x6910  br.s     loc_691A
0x6912  ldloc.s  0xB
0x6914  brfalse.s loc_691A
0x6916  ldloc.s  0xB
0x6918  stloc.s  5
0x691a  ldloc.s  6
0x691c  brfalse.s loc_6924
0x691e  ldloc.s  6
0x6920  stloc.s  4
0x6922  br.s     loc_6936
0x6924  ldloc.s  7
0x6926  brfalse.s loc_692E
0x6928  ldloc.s  7
0x692a  stloc.s  4
0x692c  br.s     loc_6936
0x692e  ldloc.s  8
0x6930  brfalse.s loc_6936
0x6932  ldloc.s  8
0x6934  stloc.s  4
0x6936  ldarg.0
0x6937  call     instance int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_RequireHttpsLevel()
0x693c  ldc.i4.0
0x693d  ble.s    loc_6975
0x693f  ldloc.s  5
0x6941  brfalse.s loc_694E
0x6943  ldloc.s  5
0x6945  stloc.2
0x6946  ldsfld   string [System]System.Uri::UriSchemeHttps
0x694b  stloc.3
0x694c  br.s     loc_698D
0x694e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6953  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x6958  brfalse.s loc_696A
0x695a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x695f  ldc.i4.1
0x6960  ldstr    aCannotFindSecu// "Cannot find secure url from reservation"...
0x6965  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x696a  ldloc.s  4
0x696c  stloc.2
0x696d  ldsfld   string [System]System.Uri::UriSchemeHttp
0x6972  stloc.3
0x6973  br.s     loc_698D
0x6975  ldloc.s  4
0x6977  brfalse.s loc_6984
0x6979  ldloc.s  4
0x697b  stloc.2
0x697c  ldsfld   string [System]System.Uri::UriSchemeHttp
0x6981  stloc.3
0x6982  br.s     loc_698D
0x6984  ldloc.s  5
0x6986  stloc.2
0x6987  ldsfld   string [System]System.Uri::UriSchemeHttps
0x698c  stloc.3
0x698d  ldloc.2
0x698e  brtrue.s loc_69AE
0x6990  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6995  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x699a  brfalse.s loc_69AC
0x699c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x69a1  ldc.i4.1
0x69a2  ldstr    aFailedToFindFu// "Failed to find full host."
0x69a7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x69ac  ldnull
0x69ad  ret
0x69ae  ldloc.3
0x69af  brtrue.s loc_69CF
0x69b1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x69b6  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x69bb  brfalse.s loc_69CD
0x69bd  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x69c2  ldc.i4.1
0x69c3  ldstr    aFailedToFindUr// "Failed to find url scheme."
0x69c8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x69cd  ldnull
0x69ce  ret
0x69cf  ldloc.3
0x69d0  ldsfld   string [System]System.Uri::SchemeDelimiter
0x69d5  ldloc.2
0x69d6  ldarg.0
0x69d7  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ReportServerVirtualDirectory()
0x69dc  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x69e1  stloc.0
0x69e2  ldloc.2
0x69e3  ldc.i4.s 0x3A
0x69e5  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x69ea  stloc.s  0xC
0x69ec  ldloc.s  0xC
0x69ee  ldc.i4.0
  ... truncated ...
```
