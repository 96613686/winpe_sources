# Microsoft.ReportingServices.Diagnostics.RSConfiguration::IsApplicationUrlSubsetOfReportServer

- ea: `0x6a00`
- end: `0x6bf0`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::IsApplicationUrlSubsetOfReportServer`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x65e0`

## callees

- `0x3450`
- `0x3640`
- `0x6a00`

## string_xrefs

- `0x6a20`: `IsApplicationUrlSubsetOfReportServer() -- Failed to get url configuration section.`
- `0x6ae5`: `IsCurrentApplicationUrlSubsetOfReportServer() -- Invalid Report Server URL in configuration: {0}`
- `0x6b8a`: `IsCurrentApplicationUrlSubsetOfReportServer() -- Invalid URL in configuration: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6a00  ldarg.1
0x6a01  ldc.i4.1
0x6a02  bne.un.s loc_6A06
0x6a04  ldc.i4.1
0x6a05  ret
0x6a06  ldarg.0
0x6a07  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration> Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_UrlConfiguration()
0x6a0c  brtrue.s loc_6A2C
0x6a0e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6a13  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x6a18  brfalse.s loc_6A2A
0x6a1a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6a1f  ldc.i4.2
0x6a20  ldstr    aIsapplicationu// "IsApplicationUrlSubsetOfReportServer() "...
0x6a25  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6a2a  ldc.i4.0
0x6a2b  ret
0x6a2c  ldarg.0
0x6a2d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration> Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_UrlConfiguration()
0x6a32  ldc.i4.1
0x6a33  ldloca.s 0
0x6a35  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::TryGetValue(var<u1>, !!T0)
0x6a3a  brtrue.s loc_6A5A
0x6a3c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6a41  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x6a46  brfalse.s loc_6A58
0x6a48  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6a4d  ldc.i4.2
0x6a4e  ldstr    aIsapplicationu_0// "IsApplicationUrlSubsetOfReportServer() "...
0x6a53  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6a58  ldc.i4.0
0x6a59  ret
0x6a5a  ldarg.0
0x6a5b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration> Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_UrlConfiguration()
0x6a60  ldarg.1
0x6a61  ldloca.s 1
0x6a63  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration>::TryGetValue(var<u1>, !!T0)
0x6a68  brtrue.s loc_6A97
0x6a6a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6a6f  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x6a74  brfalse.s loc_6A95
0x6a76  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6a7b  ldc.i4.4
0x6a7c  ldstr    aFailedToGetUrl_0// "Failed to get URL reservations for appl"...
0x6a81  ldc.i4.1
0x6a82  newarr   [mscorlib]System.Object
0x6a87  dup
0x6a88  ldc.i4.0
0x6a89  ldarg.1
0x6a8a  box      [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication
0x6a8f  stelem.ref
0x6a90  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6a95  ldc.i4.0
0x6a96  ret
0x6a97  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x6a9c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x6aa1  stloc.2
0x6aa2  ldloc.0
0x6aa3  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation[] Microsoft.ReportingServices.Diagnostics.UrlConfiguration::UrlReservations
0x6aa8  stloc.3
0x6aa9  ldc.i4.0
0x6aaa  stloc.s  4
0x6aac  br       loc_6B3D
0x6ab1  ldloc.3
0x6ab2  ldloc.s  4
0x6ab4  ldelem   Microsoft.ReportingServices.Diagnostics.UrlReservation
0x6ab9  stloc.s  5
0x6abb  ldloc.s  5
0x6abd  ldfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x6ac2  ldloca.s 6
0x6ac4  ldloca.s 7
0x6ac6  ldloca.s 8
0x6ac8  ldloca.s 9
0x6aca  ldloca.s 0xA
0x6acc  call     bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::ParseUrlPrefix(string url, [out] string& scheme, [out] string& host, [out] string& port, [out] string& prefix, [out] string& path)
0x6ad1  brtrue.s loc_6B01
0x6ad3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6ad8  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x6add  brfalse.s loc_6B37
0x6adf  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6ae4  ldc.i4.2
0x6ae5  ldstr    aIscurrentappli// "IsCurrentApplicationUrlSubsetOfReportSe"...
0x6aea  ldc.i4.1
0x6aeb  newarr   [mscorlib]System.Object
0x6af0  dup
0x6af1  ldc.i4.0
0x6af2  ldloc.s  5
0x6af4  ldfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x6af9  stelem.ref
0x6afa  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6aff  br.s     loc_6B37
0x6b01  ldc.i4.5
0x6b02  newarr   [mscorlib]System.String
0x6b07  dup
0x6b08  ldc.i4.0
0x6b09  ldloc.s  6
0x6b0b  stelem.ref
0x6b0c  dup
0x6b0d  ldc.i4.1
0x6b0e  ldsfld   string [System]System.Uri::SchemeDelimiter
0x6b13  stelem.ref
0x6b14  dup
0x6b15  ldc.i4.2
0x6b16  ldloc.s  7
0x6b18  stelem.ref
0x6b19  dup
0x6b1a  ldc.i4.3
0x6b1b  ldstr    asc_14880// ":"
0x6b20  stelem.ref
0x6b21  dup
0x6b22  ldc.i4.4
0x6b23  ldloc.s  8
0x6b25  stelem.ref
0x6b26  call     string [mscorlib]System.String::Concat(string[])
0x6b2b  stloc.s  0xB
0x6b2d  ldloc.2
0x6b2e  ldloc.s  0xB
0x6b30  ldloc.s  0xB
0x6b32  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6b37  ldloc.s  4
0x6b39  ldc.i4.1
0x6b3a  add
0x6b3b  stloc.s  4
0x6b3d  ldloc.s  4
0x6b3f  ldloc.3
0x6b40  ldlen
0x6b41  conv.i4
0x6b42  blt      loc_6AB1
0x6b47  ldloc.1
0x6b48  ldfld    valuetype Microsoft.ReportingServices.Diagnostics.UrlReservation[] Microsoft.ReportingServices.Diagnostics.UrlConfiguration::UrlReservations
0x6b4d  stloc.3
0x6b4e  ldc.i4.0
0x6b4f  stloc.s  4
0x6b51  br       loc_6BE4
0x6b56  ldloc.3
0x6b57  ldloc.s  4
0x6b59  ldelem   Microsoft.ReportingServices.Diagnostics.UrlReservation
0x6b5e  stloc.s  0xC
0x6b60  ldloc.s  0xC
0x6b62  ldfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x6b67  ldloca.s 0xD
0x6b69  ldloca.s 0xE
0x6b6b  ldloca.s 0xF
0x6b6d  ldloca.s 0x10
0x6b6f  ldloca.s 0x11
0x6b71  call     bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::ParseUrlPrefix(string url, [out] string& scheme, [out] string& host, [out] string& port, [out] string& prefix, [out] string& path)
0x6b76  brtrue.s loc_6BA6
0x6b78  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6b7d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x6b82  brfalse.s loc_6BDE
0x6b84  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6b89  ldc.i4.2
0x6b8a  ldstr    aIscurrentappli_0// "IsCurrentApplicationUrlSubsetOfReportSe"...
0x6b8f  ldc.i4.1
0x6b90  newarr   [mscorlib]System.Object
0x6b95  dup
0x6b96  ldc.i4.0
0x6b97  ldloc.s  0xC
0x6b99  ldfld    string Microsoft.ReportingServices.Diagnostics.UrlReservation::UrlPrefix
0x6b9e  stelem.ref
0x6b9f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x6ba4  br.s     loc_6BDE
0x6ba6  ldc.i4.5
0x6ba7  newarr   [mscorlib]System.String
0x6bac  dup
0x6bad  ldc.i4.0
0x6bae  ldloc.s  0xD
0x6bb0  stelem.ref
0x6bb1  dup
0x6bb2  ldc.i4.1
0x6bb3  ldsfld   string [System]System.Uri::SchemeDelimiter
0x6bb8  stelem.ref
0x6bb9  dup
0x6bba  ldc.i4.2
0x6bbb  ldloc.s  0xE
0x6bbd  stelem.ref
0x6bbe  dup
0x6bbf  ldc.i4.3
0x6bc0  ldstr    asc_14880// ":"
0x6bc5  stelem.ref
0x6bc6  dup
0x6bc7  ldc.i4.4
0x6bc8  ldloc.s  0xF
0x6bca  stelem.ref
0x6bcb  call     string [mscorlib]System.String::Concat(string[])
0x6bd0  stloc.s  0x12
0x6bd2  ldloc.2
0x6bd3  ldloc.s  0x12
0x6bd5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x6bda  brtrue.s loc_6BDE
0x6bdc  ldc.i4.0
0x6bdd  ret
0x6bde  ldloc.s  4
0x6be0  ldc.i4.1
0x6be1  add
0x6be2  stloc.s  4
0x6be4  ldloc.s  4
0x6be6  ldloc.3
0x6be7  ldlen
0x6be8  conv.i4
0x6be9  blt      loc_6B56
0x6bee  ldc.i4.1
0x6bef  ret
```
