# Microsoft.ReportingServices.Diagnostics.RSConfiguration::CheckSslAndHttpUrlReservations

- ea: `0x6cc0`
- end: `0x6d61`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::CheckSslAndHttpUrlReservations`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1c0`
- `0x5e80`

## callees

- `0x3450`
- `0x3640`
- `0x6cc0`

## pseudocode

```c

```

## disassembly

```asm
0x6cc0  ldarg.2
0x6cc1  ldc.i4.0
0x6cc2  stind.i1
0x6cc3  ldarg.3
0x6cc4  ldc.i4.0
0x6cc5  stind.i1
0x6cc6  ldarg.0
0x6cc7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration> Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_UrlConfiguration()
0x6ccc  ldarg.1
0x6ccd  ldloca.s 0
0x6ccf  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::TryGetValue(var<u1>, !!T0)
0x6cd4  brtrue.s loc_6D02
0x6cd6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6cdb  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x6ce0  brfalse.s loc_6D01
0x6ce2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6ce7  ldc.i4.4
0x6ce8  ldstr    aFailedToGetUrl_0// "Failed to get URL reservations for appl"...
0x6ced  ldc.i4.1
0x6cee  newarr   [mscorlib]System.Object
0x6cf3  dup
0x6cf4  ldc.i4.0
0x6cf5  ldarg.1
0x6cf6  box      [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication
0x6cfb  stelem.ref
0x6cfc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6d01  ret
0x6d02  ldloc.0
0x6d03  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation[] Microsoft.ReportingServices.Diagnostics.UrlConfiguration::UrlReservations
0x6d08  stloc.1
0x6d09  ldc.i4.0
0x6d0a  stloc.2
0x6d0b  br.s     loc_6D5A
0x6d0d  ldloc.1
0x6d0e  ldloc.2
0x6d0f  ldelem   Microsoft.ReportingServices.Diagnostics.UrlReservation
0x6d14  stloc.3
0x6d15  ldarg.2
0x6d16  ldind.u1
0x6d17  ldarg.3
0x6d18  ldind.u1
0x6d19  and
0x6d1a  brtrue.s loc_6D60
0x6d1c  ldloc.3
0x6d1d  ldfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x6d22  ldloca.s 4
0x6d24  ldloca.s 5
0x6d26  ldloca.s 6
0x6d28  ldloca.s 7
0x6d2a  ldloca.s 8
0x6d2c  call     bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::ParseUrlPrefix(string url, [out] string& scheme, [out] string& host, [out] string& port, [out] string& prefix, [out] string& path)
0x6d31  pop
0x6d32  ldloc.s  4
0x6d34  ldsfld   string [System]System.Uri::UriSchemeHttps
0x6d39  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6d3e  brtrue.s loc_6D45
0x6d40  ldarg.2
0x6d41  ldc.i4.1
0x6d42  stind.i1
0x6d43  br.s     loc_6D56
0x6d45  ldloc.s  4
0x6d47  ldsfld   string [System]System.Uri::UriSchemeHttp
0x6d4c  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6d51  brtrue.s loc_6D56
0x6d53  ldarg.3
0x6d54  ldc.i4.1
0x6d55  stind.i1
0x6d56  ldloc.2
0x6d57  ldc.i4.1
0x6d58  add
0x6d59  stloc.2
0x6d5a  ldloc.2
0x6d5b  ldloc.1
0x6d5c  ldlen
0x6d5d  conv.i4
0x6d5e  blt.s    loc_6D0D
0x6d60  ret
```
