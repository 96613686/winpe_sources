# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_MEMORYCACHEMISSESPERSECOND

- ea: `0x14910`
- end: `0x14925`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_MEMORYCACHEMISSESPERSECOND`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x144c0`

## string_xrefs

- `0x14915`: `MEMORYCACHEMISSESPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x14910  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager()
0x14915  ldstr    aMemorycachemis_0// "MEMORYCACHEMISSESPERSECOND"
0x1491a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceCulture
0x1491f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x14924  ret
```
