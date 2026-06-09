# Microsoft.SharePoint.Spx.WebSite.Controls.MsnWeatherService::GetWeatherDataXml

- ea: `0x15540`
- end: `0x15618`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MsnWeatherService::GetWeatherDataXml`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x15990`

## callees

- `0x7df0`
- `0x15540`

## string_xrefs

- `0x15570`: `WeatherServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0x15540  ldarg.0
0x15541  brtrue.s loc_1554E
0x15543  ldstr    aLocationcode// "locationCode"
0x15548  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1554d  throw
0x1554e  ldarg.0
0x1554f  callvirt instance string [mscorlib]System.String::Trim()
0x15554  starg.s  0
0x15556  ldarg.0
0x15557  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1555c  brtrue.s loc_15569
0x1555e  ldstr    aArgumentLocati// "Argument locationCode cannot be empty."
0x15563  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15568  throw
0x15569  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1556e  stloc.0
0x1556f  ldloc.0
0x15570  ldstr    aWeatherservice// "WeatherServiceUrl"
0x15575  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0x1557a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1557f  pop
0x15580  ldarg.1
0x15581  brfalse.s loc_155AC
0x15583  ldarg.1
0x15584  callvirt instance string [mscorlib]System.String::Trim()
0x15589  starg.s  1
0x1558b  ldarg.1
0x1558c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15591  brfalse.s loc_155AC
0x15593  ldloc.0
0x15594  ldstr    aCulture// "&culture="
0x15599  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1559e  pop
0x1559f  ldloc.0
0x155a0  ldarg.1
0x155a1  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0x155a6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x155ab  pop
0x155ac  ldarg.2
0x155ad  brfalse.s loc_155F3
0x155af  ldarg.2
0x155b0  callvirt instance string [mscorlib]System.String::Trim()
0x155b5  starg.s  2
0x155b7  ldarg.2
0x155b8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x155bd  brfalse.s loc_155F3
0x155bf  ldloc.0
0x155c0  ldstr    aWeadegreetype// "&weadegreetype="
0x155c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x155ca  pop
0x155cb  ldarg.2
0x155cc  ldstr    aMetric// "Metric"
0x155d1  ldc.i4.5
0x155d2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x155d7  brfalse.s loc_155E7
0x155d9  ldloc.0
0x155da  ldstr    aC// "C"
0x155df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x155e4  pop
0x155e5  br.s     loc_155F3
0x155e7  ldloc.0
0x155e8  ldstr    aF// "F"
0x155ed  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x155f2  pop
0x155f3  ldloc.0
0x155f4  ldstr    aWealocations// "&wealocations="
0x155f9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x155fe  pop
0x155ff  ldloc.0
0x15600  ldarg.0
0x15601  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0x15606  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1560b  pop
0x1560c  ldloc.0
0x1560d  callvirt instance string [mscorlib]System.Object::ToString()
0x15612  call     string Microsoft.SharePoint.Spx.WebSite.Controls.HtmlUtility::GetWebData(string url)
0x15617  ret
```
