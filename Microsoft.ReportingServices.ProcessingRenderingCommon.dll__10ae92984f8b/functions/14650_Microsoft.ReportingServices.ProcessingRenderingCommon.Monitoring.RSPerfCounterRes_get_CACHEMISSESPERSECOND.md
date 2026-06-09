# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_CACHEMISSESPERSECOND

- ea: `0x14650`
- end: `0x14665`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_CACHEMISSESPERSECOND`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x144c0`

## string_xrefs

- `0x14655`: `CACHEMISSESPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x14650  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager()
0x14655  ldstr    aCachemissesper// "CACHEMISSESPERSECOND"
0x1465a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceCulture
0x1465f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x14664  ret
```
