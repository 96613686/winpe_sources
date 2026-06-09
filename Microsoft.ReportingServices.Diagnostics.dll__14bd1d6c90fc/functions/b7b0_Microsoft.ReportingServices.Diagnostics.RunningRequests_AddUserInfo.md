# Microsoft.ReportingServices.Diagnostics.RunningRequests::AddUserInfo

- ea: `0xb7b0`
- end: `0xb7eb`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequests::AddUserInfo`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xb610`

## callees

- `0xb7b0`
- `0xb8c0`
- `0xbb20`
- `0xbb50`

## pseudocode

```c

```

## disassembly

```asm
0xb7b0  ldarg.0
0xb7b1  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb7b6  ldarg.1
0xb7b7  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb7bc  brtrue.s loc_B7D2
0xb7be  ldarg.0
0xb7bf  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb7c4  ldarg.1
0xb7c5  ldarg.1
0xb7c6  ldarg.2
0xb7c7  newobj   instance void Microsoft.ReportingServices.Diagnostics.UserInfo::.ctor(string userName, string reqPath)
0xb7cc  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb7d1  ret
0xb7d2  ldarg.0
0xb7d3  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb7d8  ldarg.1
0xb7d9  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb7de  castclass Microsoft.ReportingServices.Diagnostics.UserInfo
0xb7e3  ldarg.2
0xb7e4  callvirt instance bool Microsoft.ReportingServices.Diagnostics.UserInfo::AddRequest(string reqPath)
0xb7e9  pop
0xb7ea  ret
```
