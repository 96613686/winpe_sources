# Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_SNAPSHOTUPDATES

- ea: `0x14cf0`
- end: `0x14d05`
- name: `Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_SNAPSHOTUPDATES`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x144c0`

## string_xrefs

- `0x14cf5`: `SNAPSHOTUPDATES`

## pseudocode

```c

```

## disassembly

```asm
0x14cf0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::get_ResourceManager()
0x14cf5  ldstr    aSnapshotupdate// "SNAPSHOTUPDATES"
0x14cfa  ldsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.ProcessingRenderingCommon.Monitoring.RSPerfCounterRes::resourceCulture
0x14cff  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x14d04  ret
```
