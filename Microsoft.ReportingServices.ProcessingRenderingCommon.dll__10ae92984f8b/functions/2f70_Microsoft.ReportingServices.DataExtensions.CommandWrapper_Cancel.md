# Microsoft.ReportingServices.DataExtensions.CommandWrapper::Cancel

- ea: `0x2f70`
- end: `0x2fd4`
- name: `Microsoft.ReportingServices.DataExtensions.CommandWrapper::Cancel`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x2f70`
- `0x30e0`

## string_xrefs

- `0x2fc9`: `CommandWrapper.Cancel not called, connection is not valid`

## pseudocode

```c

```

## disassembly

```asm
0x2f70  ldarg.0
0x2f71  call     instance class [System.Data]System.Data.IDbCommand Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand()
0x2f76  brfalse.s loc_2FB7
0x2f78  ldarg.0
0x2f79  call     instance class [System.Data]System.Data.IDbCommand Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand()
0x2f7e  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x2f83  brfalse.s loc_2FB7
0x2f85  ldarg.0
0x2f86  call     instance class [System.Data]System.Data.IDbCommand Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand()
0x2f8b  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x2f90  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x2f95  brfalse.s loc_2FB7
0x2f97  ldarg.0
0x2f98  call     instance class [System.Data]System.Data.IDbCommand Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand()
0x2f9d  callvirt instance class [System.Data]System.Data.IDbConnection [System.Data]System.Data.IDbCommand::get_Connection()
0x2fa2  callvirt instance valuetype [System.Data]System.Data.ConnectionState [System.Data]System.Data.IDbConnection::get_State()
0x2fa7  ldc.i4.s 0x10
0x2fa9  beq.s    loc_2FB7
0x2fab  ldarg.0
0x2fac  call     instance class [System.Data]System.Data.IDbCommand Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand()
0x2fb1  callvirt instance void [System.Data]System.Data.IDbCommand::Cancel()
0x2fb6  ret
0x2fb7  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x2fbc  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x2fc1  brfalse.s loc_2FD3
0x2fc3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0x2fc8  ldc.i4.2
0x2fc9  ldstr    aCommandwrapper// "CommandWrapper.Cancel not called, conne"...
0x2fce  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2fd3  ret
```
