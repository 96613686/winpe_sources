# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat

- ea: `0x8fd0`
- end: `0x8fdc`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ThrowInvalidFormat`
- size: `12`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7390`
- `0x7d20`
- `0x8440`
- `0x8530`
- `0x85f0`
- `0x8690`
- `0x8ac0`
- `0x8c50`

## pseudocode

```c

```

## disassembly

```asm
0x8fd0  ldarg.0
0x8fd1  call     string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStringsWrapper::InvalidConfigElement(string)
0x8fd6  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x8fdb  throw
```
