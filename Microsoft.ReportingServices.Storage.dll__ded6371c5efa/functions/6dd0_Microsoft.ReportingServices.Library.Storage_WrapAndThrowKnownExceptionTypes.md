# Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes

- ea: `0x6dd0`
- end: `0x6e07`
- name: `Microsoft.ReportingServices.Library.Storage::WrapAndThrowKnownExceptionTypes`
- size: `55`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x31b0`
- `0x32f0`
- `0x3670`
- `0x3710`
- `0x37f0`
- `0x70e0`
- `0x7120`
- `0x7160`
- `0x7190`
- `0x71c0`
- `0x7210`
- `0x7550`
- `0x7580`
- `0x76d0`
- `0x76f0`
- `0x7710`

## callees

- `0x6dd0`

## pseudocode

```c

```

## disassembly

```asm
0x6dd0  ldarg.0
0x6dd1  brtrue.s loc_6DD4
0x6dd3  ret
0x6dd4  ldarg.0
0x6dd5  isinst   [mscorlib]System.InvalidOperationException
0x6dda  brfalse.s loc_6DF6
0x6ddc  ldarg.0
0x6ddd  callvirt instance string [mscorlib]System.Exception::get_Source()
0x6de2  ldstr    aSystemData// "System.Data"
0x6de7  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x6dec  brtrue.s loc_6E06
0x6dee  ldarg.0
0x6def  ldnull
0x6df0  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::.ctor(class [mscorlib]System.Exception, string)
0x6df5  throw
0x6df6  ldarg.0
0x6df7  isinst   [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlException
0x6dfc  brfalse.s loc_6E06
0x6dfe  ldarg.0
0x6dff  ldnull
0x6e00  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::.ctor(class [mscorlib]System.Exception, string)
0x6e05  throw
0x6e06  ret
```
