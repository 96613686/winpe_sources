# Microsoft.Reporting.WebForms.ClientTelemetry::GetRenderEvent

- ea: `0x23160`
- end: `0x231bb`
- name: `Microsoft.Reporting.WebForms.ClientTelemetry::GetRenderEvent`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x33c60`

## callees

- `0x23110`

## string_xrefs

- `0x23193`: `UserAgent`
- `0x2317d`: `ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x23160  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x23165  dup
0x23166  ldstr    aTargetinghtml4// "TargetingHtml40"
0x2316b  ldarga.s 2
0x2316d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23172  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x23177  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2317c  dup
0x2317d  ldstr    aItempath// "ItemPath"
0x23182  ldsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RegistryTelemetryConfiguration Microsoft.Reporting.WebForms.ClientTelemetry::SqlConfiguration
0x23187  ldarg.1
0x23188  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.RegistryTelemetryConfiguration::GetSHA256Hash(string)
0x2318d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x23192  dup
0x23193  ldstr    aUseragent// "UserAgent"
0x23198  ldarg.0
0x23199  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Reporting.WebForms.ClientTelemetry::Context
0x2319e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x231a3  callvirt instance string [System.Web]System.Web.HttpRequest::get_UserAgent()
0x231a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x231ad  stloc.0
0x231ae  ldarg.0
0x231af  ldstr    aRsReportviewer// "RS.ReportViewer.Render"
0x231b4  ldloc.0
0x231b5  call     instance class [System.Web]System.Web.UI.LiteralControl Microsoft.Reporting.WebForms.ClientTelemetry::GetEventJs(string eventName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> properties)
0x231ba  ret
```
