# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_MODELCACHEHITS

- ea: `0x14970`
- end: `0x14985`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_MODELCACHEHITS`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x144c0`

## string_xrefs

- `0x14975`: `MODELCACHEHITS`

## pseudocode

```c

```

## disassembly

```asm
0x14970  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager()
0x14975  ldstr    aModelcachehits// "MODELCACHEHITS"
0x1497a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceCulture
0x1497f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x14984  ret
```
