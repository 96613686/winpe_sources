# Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp

- ea: `0xb8c0`
- end: `0xb8da`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp`
- size: `26`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb680`
- `0xb6d0`
- `0xb7b0`
- `0xb830`

## callees

- `0xb8c0`

## pseudocode

```c

```

## disassembly

```asm
0xb8c0  ldarg.0
0xb8c1  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::m_users
0xb8c6  brtrue.s loc_B8D3
0xb8c8  ldarg.0
0xb8c9  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0xb8ce  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::m_users
0xb8d3  ldarg.0
0xb8d4  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::m_users
0xb8d9  ret
```
