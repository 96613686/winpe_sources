# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_UPDATESCHEDULEEVENTSPROCESSED

- ea: `0x14d70`
- end: `0x14d85`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_UPDATESCHEDULEEVENTSPROCESSED`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x144c0`

## string_xrefs

- `0x14d75`: `UPDATESCHEDULEEVENTSPROCESSED`

## pseudocode

```c

```

## disassembly

```asm
0x14d70  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager()
0x14d75  ldstr    aUpdateschedule// "UPDATESCHEDULEEVENTSPROCESSED"
0x14d7a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceCulture
0x14d7f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x14d84  ret
```
