# Microsoft.ReportingServices.Diagnostics.RunningRequests::ActiveRequestsForUser

- ea: `0xb680`
- end: `0xb6c2`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequests::ActiveRequestsForUser`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xb610`

## callees

- `0xb680`
- `0xb8c0`
- `0xbbe0`

## pseudocode

```c

```

## disassembly

```asm
0xb680  ldarg.0
0xb681  stloc.0
0xb682  ldc.i4.0
0xb683  stloc.1
0xb684  ldloc.0
0xb685  ldloca.s 1
0xb687  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xb68c  ldc.i4.0
0xb68d  stloc.2
0xb68e  ldarg.0
0xb68f  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_UserInfoProp()
0xb694  ldarg.1
0xb695  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb69a  stloc.3
0xb69b  ldloc.3
0xb69c  brfalse.s loc_B6B0
0xb69e  ldloc.3
0xb69f  castclass Microsoft.ReportingServices.Diagnostics.UserInfo
0xb6a4  stloc.s  4
0xb6a6  ldloc.2
0xb6a7  ldloc.s  4
0xb6a9  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.UserInfo::get_TotalRequests()
0xb6ae  add
0xb6af  stloc.2
0xb6b0  ldloc.2
0xb6b1  stloc.s  5
0xb6b3  leave.s  loc_B6BF
0xb6b5  ldloc.1
0xb6b6  brfalse.s loc_B6BE
0xb6b8  ldloc.0
0xb6b9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xb6be  endfinally
0xb6bf  ldloc.s  5
0xb6c1  ret
```
