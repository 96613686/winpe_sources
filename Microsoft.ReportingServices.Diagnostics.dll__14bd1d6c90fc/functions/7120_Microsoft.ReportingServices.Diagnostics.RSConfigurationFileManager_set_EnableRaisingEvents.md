# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::set_EnableRaisingEvents

- ea: `0x7120`
- end: `0x7131`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::set_EnableRaisingEvents`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x7126`: `Cannot enable raising events from RSConfigurationFileManager.`

## pseudocode

```c

```

## disassembly

```asm
0x7120  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x7125  ldc.i4.0
0x7126  ldstr    aCannotEnableRa// "Cannot enable raising events from RSCon"...
0x712b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x7130  ret
```
