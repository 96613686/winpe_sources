# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_CACHEMISSES

- ea: `0x14630`
- end: `0x14645`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_CACHEMISSES`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x144c0`

## string_xrefs

- `0x14635`: `CACHEMISSES`

## pseudocode

```c

```

## disassembly

```asm
0x14630  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager()
0x14635  ldstr    aCachemisses// "CACHEMISSES"
0x1463a  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceCulture
0x1463f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x14644  ret
```
