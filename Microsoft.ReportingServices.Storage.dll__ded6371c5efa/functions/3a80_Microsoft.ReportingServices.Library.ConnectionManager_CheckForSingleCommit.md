# Microsoft.ReportingServices.Library.ConnectionManager::CheckForSingleCommit

- ea: `0x3a80`
- end: `0x3a9c`
- name: `Microsoft.ReportingServices.Library.ConnectionManager::CheckForSingleCommit`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3710`
- `0x37f0`

## callees

- `0x3270`
- `0x3a80`

## string_xrefs

- `0x3a90`: `Multiple commit/rollback operations performed on SingleCommit connection manager.`

## pseudocode

```c

```

## disassembly

```asm
0x3a80  ldarg.0
0x3a81  call     instance bool Microsoft.ReportingServices.Library.ConnectionManager::get_SingleCommitEnabled()
0x3a86  brfalse.s loc_3A9B
0x3a88  ldarg.0
0x3a89  ldfld    bool Microsoft.ReportingServices.Library.ConnectionManager::_performedCommitOrRollback
0x3a8e  brfalse.s loc_3A9B
0x3a90  ldstr    aMultipleCommit// "Multiple commit/rollback operations per"...
0x3a95  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x3a9a  throw
0x3a9b  ret
```
