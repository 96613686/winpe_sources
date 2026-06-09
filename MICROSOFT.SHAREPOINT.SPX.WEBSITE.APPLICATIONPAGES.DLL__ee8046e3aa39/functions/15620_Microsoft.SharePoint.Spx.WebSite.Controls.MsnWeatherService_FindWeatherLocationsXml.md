# Microsoft.SharePoint.Spx.WebSite.Controls.MsnWeatherService::FindWeatherLocationsXml

- ea: `0x15620`
- end: `0x156f3`
- name: `Microsoft.SharePoint.Spx.WebSite.Controls.MsnWeatherService::FindWeatherLocationsXml`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb50`
- `0x15990`

## callees

- `0x7df0`
- `0x15620`

## string_xrefs

- `0x15650`: `http://weather.service.msn.com/data.aspx?src=Office_Live&outputview=search`

## pseudocode

```c

```

## disassembly

```asm
0x15620  ldarg.0
0x15621  brtrue.s loc_1562E
0x15623  ldstr    aSearchstr_0// "searchStr"
0x15628  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1562d  throw
0x1562e  ldarg.0
0x1562f  callvirt instance string [mscorlib]System.String::Trim()
0x15634  starg.s  0
0x15636  ldarg.0
0x15637  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1563c  brtrue.s loc_15649
0x1563e  ldstr    aArgumentSearch// "Argument searchStr cannot be empty."
0x15643  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15648  throw
0x15649  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1564e  stloc.0
0x1564f  ldloc.0
0x15650  ldstr    aHttpWeatherSer// "http://weather.service.msn.com/data.asp"...
0x15655  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1565a  pop
0x1565b  ldarg.1
0x1565c  brfalse.s loc_15687
0x1565e  ldarg.1
0x1565f  callvirt instance string [mscorlib]System.String::Trim()
0x15664  starg.s  1
0x15666  ldarg.1
0x15667  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1566c  brfalse.s loc_15687
0x1566e  ldloc.0
0x1566f  ldstr    aCulture// "&culture="
0x15674  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15679  pop
0x1567a  ldloc.0
0x1567b  ldarg.1
0x1567c  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0x15681  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15686  pop
0x15687  ldarg.2
0x15688  brfalse.s loc_156CE
0x1568a  ldarg.2
0x1568b  callvirt instance string [mscorlib]System.String::Trim()
0x15690  starg.s  2
0x15692  ldarg.2
0x15693  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15698  brfalse.s loc_156CE
0x1569a  ldloc.0
0x1569b  ldstr    aWeadegreetype// "&weadegreetype="
0x156a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x156a5  pop
0x156a6  ldarg.2
0x156a7  ldstr    aMetric// "Metric"
0x156ac  ldc.i4.5
0x156ad  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x156b2  brfalse.s loc_156C2
0x156b4  ldloc.0
0x156b5  ldstr    aC// "C"
0x156ba  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x156bf  pop
0x156c0  br.s     loc_156CE
0x156c2  ldloc.0
0x156c3  ldstr    aF// "F"
0x156c8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x156cd  pop
0x156ce  ldloc.0
0x156cf  ldstr    aWeasearchstr// "&weasearchstr="
0x156d4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x156d9  pop
0x156da  ldloc.0
0x156db  ldarg.0
0x156dc  call     string [AntiXSSLibrary]Microsoft.Security.Application.AntiXss::UrlEncode(string)
0x156e1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x156e6  pop
0x156e7  ldloc.0
0x156e8  callvirt instance string [mscorlib]System.Object::ToString()
0x156ed  call     string Microsoft.SharePoint.Spx.WebSite.Controls.HtmlUtility::GetWebData(string url)
0x156f2  ret
```
