# Microsoft.ReportingServices.Library.ConnectionManager::get_ConnectionString

- ea: `0x3930`
- end: `0x3941`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::get_ConnectionString`
- size: `17`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3180`
- `0x3360`
- `0x33a0`
- `0x3970`
- `0x3a60`

## callees

- `0x7c40`

## pseudocode

```c

```

## disassembly

```asm
0x3930  ldarg.0
0x3931  ldfld    class Microsoft.ReportingServices.Library.ConnectionConfig Microsoft.ReportingServices.Library.ConnectionManager::_config
0x3936  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SecureStringWrapper Microsoft.ReportingServices.Library.ConnectionConfig::get_ConnectionString()
0x393b  callvirt instance string [mscorlib]System.Object::ToString()
0x3940  ret
```
