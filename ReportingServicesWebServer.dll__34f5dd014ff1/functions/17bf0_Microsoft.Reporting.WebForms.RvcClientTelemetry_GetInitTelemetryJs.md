# Microsoft.Reporting.WebForms.RvcClientTelemetry::GetInitTelemetryJs

- ea: `0x17bf0`
- end: `0x17c17`
- name: `Microsoft.Reporting.WebForms.RvcClientTelemetry::GetInitTelemetryJs`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14110`

## callees

- `0x17b70`

## string_xrefs

- `0x17c01`: `Microsoft.Reporting.WebForms.Templates.InitTelemetry.js`
- `0x17c0b`: `[TelemetryConfig]`

## pseudocode

```c

```

## disassembly

```asm
0x17bf0  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x17bf5  ldarg.0
0x17bf6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Reporting.WebForms.RvcClientTelemetry::_telemetryConfiguration
0x17bfb  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x17c00  stloc.0
0x17c01  ldstr    aMicrosoftRepor_118// "Microsoft.Reporting.WebForms.Templates."...
0x17c06  call     string Microsoft.Reporting.WebForms.ResourceReader::GetResource(string resourceFullPath)
0x17c0b  ldstr    aTelemetryconfi// "[TelemetryConfig]"
0x17c10  ldloc.0
0x17c11  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x17c16  ret
```
