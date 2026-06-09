# Microsoft.ReportingServices.Diagnostics.RunningRequests::RemoveUserInfo

- ea: `0xb830`
- end: `0xb861`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequests::RemoveUserInfo`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xb650`

## callees

- `0xb830`
- `0xb8c0`
- `0xbba0`
- `0xbc30`

## pseudocode

```c

```

## disassembly

```asm
0xb830  ldarg.0
0xb831  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb836  ldarg.1
0xb837  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb83c  stloc.0
0xb83d  ldloc.0
0xb83e  brfalse.s loc_B860
0xb840  ldloc.0
0xb841  castclass Microsoft.ReportingServices.Diagnostics.UserInfo
0xb846  dup
0xb847  ldarg.2
0xb848  callvirt instance void Microsoft.ReportingServices.Diagnostics.UserInfo::RemoveRequest(string reqPath)
0xb84d  callvirt instance bool Microsoft.ReportingServices.Diagnostics.UserInfo::IsEmpty()
0xb852  brfalse.s loc_B860
0xb854  ldarg.0
0xb855  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb85a  ldarg.1
0xb85b  callvirt instance void [mscorlib]System.Collections.Hashtable::Remove(object)
0xb860  ret
```
