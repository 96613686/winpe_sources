# Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add

- ea: `0x1700`
- end: `0x170a`
- name: `Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add`
- size: `10`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7390`
- `0x8ac0`
- `0x8c50`

## callees

- `0x1710`

## pseudocode

```c

```

## disassembly

```asm
0x1700  ldarg.0
0x1701  ldarg.1
0x1702  ldarg.2
0x1703  ldnull
0x1704  call     instance void Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag::Add(valuetype Microsoft.ReportingServices.Diagnostics.ConfigurationProperty propertyId, string value, string name)
0x1709  ret
```
