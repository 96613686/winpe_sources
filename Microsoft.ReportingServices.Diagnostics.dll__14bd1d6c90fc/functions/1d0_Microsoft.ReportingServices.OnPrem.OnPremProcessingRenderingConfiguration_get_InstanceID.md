# Microsoft.ReportingServices.OnPrem.OnPremProcessingRenderingConfiguration::get_InstanceID

- ea: `0x1d0`
- end: `0x1dc`
- name: `Microsoft.ReportingServices.OnPrem.OnPremProcessingRenderingConfiguration::get_InstanceID`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x160`
- `0x170`
- `0x1a0`

## callees

- `0x33c0`

## pseudocode

```c

```

## disassembly

```asm
0x1d0  ldarg.0
0x1d1  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.OnPrem.OnPremProcessingRenderingConfiguration::WrappedConfig
0x1d6  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x1db  ret
```
