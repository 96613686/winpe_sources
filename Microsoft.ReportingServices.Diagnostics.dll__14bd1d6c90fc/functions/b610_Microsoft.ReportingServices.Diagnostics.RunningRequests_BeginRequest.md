# Microsoft.ReportingServices.Diagnostics.RunningRequests::BeginRequest

- ea: `0xb610`
- end: `0xb64a`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequests::BeginRequest`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xb610`
- `0xb680`
- `0xb7b0`
- `0xb7f0`

## pseudocode

```c

```

## disassembly

```asm
0xb610  ldarg.0
0xb611  stloc.0
0xb612  ldc.i4.0
0xb613  stloc.1
0xb614  ldloc.0
0xb615  ldloca.s 1
0xb617  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xb61c  ldarg.0
0xb61d  ldarg.2
0xb61e  call     instance int32 Microsoft.ReportingServices.Diagnostics.RunningRequests::ActiveRequestsForUser(string userName)
0xb623  ldarg.3
0xb624  ble.s    loc_B62A
0xb626  ldc.i4.0
0xb627  stloc.2
0xb628  leave.s  loc_B648
0xb62a  ldarg.0
0xb62b  ldarg.2
0xb62c  ldarg.1
0xb62d  call     instance void Microsoft.ReportingServices.Diagnostics.RunningRequests::AddUserInfo(string userName, string reqPath)
0xb632  ldarg.0
0xb633  ldarg.2
0xb634  ldarg.1
0xb635  call     instance void Microsoft.ReportingServices.Diagnostics.RunningRequests::AddReqInfo(string userName, string reqPath)
0xb63a  ldc.i4.1
0xb63b  stloc.2
0xb63c  leave.s  loc_B648
0xb63e  ldloc.1
0xb63f  brfalse.s loc_B647
0xb641  ldloc.0
0xb642  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xb647  endfinally
0xb648  ldloc.2
0xb649  ret
```
