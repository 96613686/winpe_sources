# Microsoft.ReportingServices.Diagnostics.ApplicationParameter::get_BaseValue

- ea: `0x1240`
- end: `0x12a4`
- name: `Microsoft.ReportingServices.Diagnostics.ApplicationParameter::get_BaseValue`
- size: `100`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1570`
- `0x15a0`
- `0x1860`
- `0x1950`
- `0x2870`
- `0x93a0`
- `0x9450`

## callees

- `0x1200`
- `0x1210`
- `0x1240`
- `0x1350`

## pseudocode

```c

```

## disassembly

```asm
0x1240  ldarg.0
0x1241  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_ParameterSource
0x1246  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource::get_UseExternalStore()
0x124b  brfalse.s loc_128F
0x124d  ldarg.0
0x124e  ldarg.0
0x124f  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_ParameterSource
0x1254  ldarg.0
0x1255  ldfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_name
0x125a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IParameterSource::GetParameter(string)
0x125f  stfld    string Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_configValue
0x1264  ldarg.0
0x1265  call     instance bool Microsoft.ReportingServices.Diagnostics.ApplicationParameter::get_TraceSuccess()
0x126a  stloc.0
0x126b  ldarg.0
0x126c  ldc.i4.0
0x126d  stfld    bool Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_traceUsingDefault
0x1272  ldarg.0
0x1273  ldc.i4.0
0x1274  call     instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool value)
0x1279  ldarg.0
0x127a  call     instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::InterpretValue()
0x127f  ldarg.0
0x1280  ldloc.0
0x1281  call     instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::set_TraceSuccess(bool value)
0x1286  ldarg.0
0x1287  ldc.i4.1
0x1288  stfld    bool Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_traceUsingDefault
0x128d  br.s     loc_129D
0x128f  ldarg.0
0x1290  ldfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseValue
0x1295  brtrue.s loc_129D
0x1297  ldarg.0
0x1298  call     instance void Microsoft.ReportingServices.Diagnostics.ApplicationParameter::InterpretValue()
0x129d  ldarg.0
0x129e  ldfld    object Microsoft.ReportingServices.Diagnostics.ApplicationParameter::m_BaseValue
0x12a3  ret
```
