# Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::IsSecureMethod

- ea: `0x1be50`
- end: `0x1beae`
- name: `Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::IsSecureMethod`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bb90`
- `0x1bbd0`
- `0x1bd00`

## callees

- `0x1bde0`
- `0x1be50`
- `0x24260`

## pseudocode

```c

```

## disassembly

```asm
0x1be50  ldarg.0
0x1be51  ldfld    bool Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::m_alwaysUseSSL
0x1be56  brfalse.s loc_1BE5A
0x1be58  ldc.i4.1
0x1be59  ret
0x1be5a  ldarg.0
0x1be5b  ldfld    class SecureMethodsList Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::m_secureMethods
0x1be60  brtrue.s loc_1BEA1
0x1be62  ldarg.0
0x1be63  call     instance string[] Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::GetSecureMethods()
0x1be68  stloc.0
0x1be69  ldarg.0
0x1be6a  ldfld    bool Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::m_alwaysUseSSL
0x1be6f  brtrue.s loc_1BE9F
0x1be71  ldarg.0
0x1be72  newobj   instance void SecureMethodsList::.ctor()
0x1be77  stfld    class SecureMethodsList Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::m_secureMethods
0x1be7c  ldloc.0
0x1be7d  stloc.1
0x1be7e  ldc.i4.0
0x1be7f  stloc.2
0x1be80  br.s     loc_1BE97
0x1be82  ldloc.1
0x1be83  ldloc.2
0x1be84  ldelem.ref
0x1be85  stloc.3
0x1be86  ldarg.0
0x1be87  ldfld    class SecureMethodsList Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::m_secureMethods
0x1be8c  ldloc.3
0x1be8d  ldnull
0x1be8e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1be93  ldloc.2
0x1be94  ldc.i4.1
0x1be95  add
0x1be96  stloc.2
0x1be97  ldloc.2
0x1be98  ldloc.1
0x1be99  ldlen
0x1be9a  conv.i4
0x1be9b  blt.s    loc_1BE82
0x1be9d  br.s     loc_1BEA1
0x1be9f  ldc.i4.1
0x1bea0  ret
0x1bea1  ldarg.0
0x1bea2  ldfld    class SecureMethodsList Microsoft.SqlServer.ReportingServices2005.Execution.RSExecutionConnection::m_secureMethods
0x1bea7  ldarg.1
0x1bea8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1bead  ret
```
