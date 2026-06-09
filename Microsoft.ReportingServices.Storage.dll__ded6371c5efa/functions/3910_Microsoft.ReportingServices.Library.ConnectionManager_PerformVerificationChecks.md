# Microsoft.ReportingServices.Library.ConnectionManager::PerformVerificationChecks

- ea: `0x3910`
- end: `0x3924`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::PerformVerificationChecks`
- size: `20`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x3180`
- `0x3360`
- `0x33a0`
- `0x3bd0`

## callees

- `0x3910`

## string_xrefs

- `0x3918`: `Connection access outside guarded area.`

## pseudocode

```c

```

## disassembly

```asm
0x3910  ldarg.0
0x3911  ldfld    bool Microsoft.ReportingServices.Library.ConnectionManager::_willDisconnectStorage
0x3916  brtrue.s loc_3923
0x3918  ldstr    aConnectionAcce// "Connection access outside guarded area."
0x391d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x3922  throw
0x3923  ret
```
