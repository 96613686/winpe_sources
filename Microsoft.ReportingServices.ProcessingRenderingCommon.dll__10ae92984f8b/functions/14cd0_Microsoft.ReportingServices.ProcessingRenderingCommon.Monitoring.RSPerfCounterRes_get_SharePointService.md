# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_SharePointService

- ea: `0x14cd0`
- end: `0x14ce5`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_SharePointService`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x144c0`

## string_xrefs

- `0x14cd5`: `SharePointService`

## pseudocode

```c

```

## disassembly

```asm
0x14cd0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager()
0x14cd5  ldstr    aSharepointserv// "SharePointService"
0x14cda  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceCulture
0x14cdf  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x14ce4  ret
```
