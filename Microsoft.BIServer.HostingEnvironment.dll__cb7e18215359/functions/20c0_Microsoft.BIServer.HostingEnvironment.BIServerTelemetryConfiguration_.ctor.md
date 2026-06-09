# Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::.ctor

- ea: `0x20c0`
- end: `0x214e`
- name: `Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::.ctor`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x21a0`
- `0x21c0`
- `0x21d0`
- `0x21e0`
- `0x2250`

## pseudocode

```c

```

## disassembly

```asm
0x20c0  ldarg.0
0x20c1  call     instance void [mscorlib]System.Object::.ctor()
0x20c6  ldarg.0
0x20c7  ldarg.1
0x20c8  stfld    string Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::_instanceName
0x20cd  ldarg.0
0x20ce  call     string [Microsoft.BIServer.Telemetry]Microsoft.BIServer.Telemetry.Helpers.TelemetryUtils::GetProductVersion()
0x20d3  call     instance void Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::set_Build(string value)
0x20d8  ldarg.0
0x20d9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x20de  call     instance void Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::set_AdditionalProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x20e3  ldarg.0
0x20e4  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::get_AdditionalProperties()
0x20e9  ldstr    aIspublicbuild// "IsPublicBuild"
0x20ee  ldarg.0
0x20ef  call     instance bool Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::IsPublicBuild()
0x20f4  stloc.1
0x20f5  ldloca.s 1
0x20f7  call     instance string [mscorlib]System.Boolean::ToString()
0x20fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2101  newobj   instance void [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::.ctor()
0x2106  ldarg.1
0x2107  callvirt instance class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStore::Load(string)
0x210c  stloc.0
0x210d  ldarg.0
0x210e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::get_AdditionalProperties()
0x2113  ldstr    aEdition// "Edition"
0x2118  ldloc.0
0x2119  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_SkuType()
0x211e  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetStrings(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x2123  callvirt instance string [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings::get_ShortName()
0x2128  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x212d  ldarg.0
0x212e  ldloc.0
0x212f  callvirt instance valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuInfo::get_SkuType()
0x2134  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetDetails(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType)
0x2139  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuDetails::Product
0x213e  call     class [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.EnumExtensions::GetStrings(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.ProductType)
0x2143  ldfld    string [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuStrings::FullName
0x2148  call     instance void Microsoft.BIServer.HostingEnvironment.BIServerTelemetryConfiguration::set_Product(string value)
0x214d  ret
```
