# Microsoft.ReportingServices.Diagnostics.RegistryTelemetryConfiguration::get_SqlRegistryRoot

- ea: `0xb480`
- end: `0xb4c0`
- name: `Microsoft.ReportingServices.Diagnostics.RegistryTelemetryConfiguration::get_SqlRegistryRoot`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10b20`

## string_xrefs

- `0xb4aa`: `Reading CPE key from {0}`

## pseudocode

```c

```

## disassembly

```asm
0xb480  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb485  ldstr    aSoftwareMicros_0// "Software\\Microsoft\\Microsoft SQL Serv"...
0xb48a  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0xb48f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_InstanceID()
0xb494  ldstr    aCpe// "\\CPE"
0xb499  call     string [mscorlib]System.String::Concat(string, string)
0xb49e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xb4a3  stloc.0
0xb4a4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0xb4a9  ldc.i4.4
0xb4aa  ldstr    aReadingCpeKeyF// "Reading CPE key from {0}"
0xb4af  ldc.i4.1
0xb4b0  newarr   [mscorlib]System.Object
0xb4b5  dup
0xb4b6  ldc.i4.0
0xb4b7  ldloc.0
0xb4b8  stelem.ref
0xb4b9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xb4be  ldloc.0
0xb4bf  ret
```
