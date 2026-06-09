# Microsoft.ReportingServices.Library.Query::.ctor_0

- ea: `0x3b50`
- end: `0x3bd8`
- name: `Microsoft.ReportingServices.Library.Query::.ctor_0`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3890`

## callees

- `0x3b50`

## string_xrefs

- `0x3ba1`: `CommandType`
- `0x3bcc`: `CommandText`

## pseudocode

```c

```

## disassembly

```asm
0x3b50  ldarg.0
0x3b51  ldstr    aText// "Text"
0x3b56  stfld    string Microsoft.ReportingServices.Library.Query::CommandType
0x3b5b  ldarg.0
0x3b5c  call     instance void [mscorlib]System.Object::.ctor()
0x3b61  ldarg.1
0x3b62  brtrue.s loc_3B6F
0x3b64  ldstr    aQuery// "Query"
0x3b69  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingElementException::.ctor(string)
0x3b6e  throw
0x3b6f  ldarg.0
0x3b70  ldarg.1
0x3b71  ldfld    string Microsoft.ReportingServices.Library.Soap.QueryDefinition::CommandText
0x3b76  stfld    string Microsoft.ReportingServices.Library.Query::CommandText
0x3b7b  ldarg.0
0x3b7c  ldarg.1
0x3b7d  ldfld    int32 Microsoft.ReportingServices.Library.Soap.QueryDefinition::Timeout
0x3b82  stfld    int32 Microsoft.ReportingServices.Library.Query::Timeout
0x3b87  ldarg.1
0x3b88  ldfld    string Microsoft.ReportingServices.Library.Soap.QueryDefinition::CommandType
0x3b8d  brfalse.s loc_3BAC
0x3b8f  ldarg.1
0x3b90  ldfld    string Microsoft.ReportingServices.Library.Soap.QueryDefinition::CommandType
0x3b95  ldstr    aText// "Text"
0x3b9a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3b9f  brfalse.s loc_3BAC
0x3ba1  ldstr    aCommandtype// "CommandType"
0x3ba6  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x3bab  throw
0x3bac  ldarg.0
0x3bad  ldfld    string Microsoft.ReportingServices.Library.Query::CommandText
0x3bb2  brtrue.s loc_3BBA
0x3bb4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidXmlException::.ctor()
0x3bb9  throw
0x3bba  ldarg.0
0x3bbb  ldfld    string Microsoft.ReportingServices.Library.Query::CommandText
0x3bc0  ldsfld   string [mscorlib]System.String::Empty
0x3bc5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3bca  brfalse.s loc_3BD7
0x3bcc  ldstr    aCommandtext// "CommandText"
0x3bd1  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidElementException::.ctor(string)
0x3bd6  throw
0x3bd7  ret
```
