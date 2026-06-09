# Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::.ctor

- ea: `0x6ef0`
- end: `0x6f18`
- name: `Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::.ctor`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x70b0`

## string_xrefs

- `0x6eff`: `command`

## pseudocode

```c

```

## disassembly

```asm
0x6ef0  ldarg.0
0x6ef1  call     instance void [mscorlib]System.Object::.ctor()
0x6ef6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x6efb  ldarg.1
0x6efc  ldnull
0x6efd  cgt.un
0x6eff  ldstr    aCommand_0// "command"
0x6f04  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x6f09  ldarg.0
0x6f0a  ldarg.1
0x6f0b  stfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::m_command
0x6f10  ldarg.0
0x6f11  ldarg.2
0x6f12  stfld    class [mscorlib]System.IDisposable Microsoft.ReportingServices.Library.ThreadSafeSqlCommand::m_lockContext
0x6f17  ret
```
