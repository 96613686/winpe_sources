# Microsoft.ReportingServices.Diagnostics.RunningRequests::RemoveRequestInfo

- ea: `0xb870`
- end: `0xb8a1`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequests::RemoveRequestInfo`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xb650`

## callees

- `0xb870`
- `0xb8e0`
- `0xb9a0`
- `0xba50`

## pseudocode

```c

```

## disassembly

```asm
0xb870  ldarg.0
0xb871  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_RequestInfoProp()
0xb876  ldarg.2
0xb877  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb87c  stloc.0
0xb87d  ldloc.0
0xb87e  brfalse.s loc_B8A0
0xb880  ldloc.0
0xb881  castclass Microsoft.ReportingServices.Diagnostics.ReqInfo
0xb886  dup
0xb887  ldarg.1
0xb888  callvirt instance void Microsoft.ReportingServices.Diagnostics.ReqInfo::RemoveRequest(string userName)
0xb88d  callvirt instance bool Microsoft.ReportingServices.Diagnostics.ReqInfo::IsEmpty()
0xb892  brfalse.s loc_B8A0
0xb894  ldarg.0
0xb895  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_RequestInfoProp()
0xb89a  ldarg.2
0xb89b  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0xb8a0  ret
```
