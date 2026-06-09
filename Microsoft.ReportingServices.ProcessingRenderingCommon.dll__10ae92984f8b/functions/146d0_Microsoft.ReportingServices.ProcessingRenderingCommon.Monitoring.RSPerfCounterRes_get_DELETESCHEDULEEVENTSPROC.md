# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_DELETESCHEDULEEVENTSPROCESSED

- ea: `0x146d0`
- end: `0x146e5`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_DELETESCHEDULEEVENTSPROCESSED`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x144c0`

## string_xrefs

- `0x146d5`: `DELETESCHEDULEEVENTSPROCESSED`

## pseudocode

```c

```

## disassembly

```asm
0x146d0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager()
0x146d5  ldstr    aDeleteschedule// "DELETESCHEDULEEVENTSPROCESSED"
0x146da  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceCulture
0x146df  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x146e4  ret
```
