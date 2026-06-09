# Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::Dispose

- ea: `0x6f20`
- end: `0x6f35`
- name: `Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::Dispose`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x71f0`

## callees

- `0x6f20`
- `0x6f40`

## pseudocode

```c

```

## disassembly

```asm
0x6f20  ldarg.0
0x6f21  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::m_command
0x6f26  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x6f2b  leave.s  loc_6F34
0x6f2d  ldarg.0
0x6f2e  call     instance void Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::ReleaseLockContext()
0x6f33  endfinally
0x6f34  ret
```
