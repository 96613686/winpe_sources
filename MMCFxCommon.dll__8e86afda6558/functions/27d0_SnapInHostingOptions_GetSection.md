# SnapInHostingOptions::GetSection

- ea: `0x27d0`
- end: `0x2826`
- name: `SnapInHostingOptions::GetSection`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x2680`

## callees

- `0xa0`
- `0x27d0`

## string_xrefs

- `0x27ef`: `mmc.exe.config: section <appSettings> does not exist`
- `0x2803`: `mmc.exe.config: ConfigurationException thrown reading section appSettings. It should be declared as <appSettings>.  Exception message : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x27d0  ldsfld   class [System]System.Collections.Specialized.NameValueCollection SnapInHostingOptions::_section
0x27d5  brtrue.s loc_2820
0x27d7  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x27dc  stsfld   class [System]System.Collections.Specialized.NameValueCollection SnapInHostingOptions::_section
0x27e1  ldsfld   class [System]System.Collections.Specialized.NameValueCollection SnapInHostingOptions::_section
0x27e6  brtrue.s loc_27F9
0x27e8  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x27ed  ldc.i4.8
0x27ee  ldc.i4.0
0x27ef  ldstr    aMmcExeConfigSe// "mmc.exe.config: section <appSettings> d"...
0x27f4  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0x27f9  leave.s  loc_2820
0x27fb  stloc.0
0x27fc  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x2801  ldc.i4.4
0x2802  ldc.i4.0
0x2803  ldstr    aMmcExeConfigCo// "mmc.exe.config: ConfigurationException "...
0x2808  ldc.i4.1
0x2809  newarr   [mscorlib]System.Object
0x280e  stloc.1
0x280f  ldloc.1
0x2810  ldc.i4.0
0x2811  ldloc.0
0x2812  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2817  stelem.ref
0x2818  ldloc.1
0x2819  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0x281e  leave.s  loc_2820
0x2820  ldsfld   class [System]System.Collections.Specialized.NameValueCollection SnapInHostingOptions::_section
0x2825  ret
```
