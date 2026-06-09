# Microsoft.ReportingServices.Diagnostics.RunningRequests::AddReqInfo

- ea: `0xb7f0`
- end: `0xb82b`
- name: `Microsoft.ReportingServices.Diagnostics.RunningRequests::AddReqInfo`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xb610`

## callees

- `0xb7f0`
- `0xb8e0`
- `0xb920`
- `0xb950`

## pseudocode

```c

```

## disassembly

```asm
0xb7f0  ldarg.0
0xb7f1  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_RequestInfoProp()
0xb7f6  ldarg.2
0xb7f7  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb7fc  brtrue.s loc_B812
0xb7fe  ldarg.0
0xb7ff  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_RequestInfoProp()
0xb804  ldarg.2
0xb805  ldarg.1
0xb806  ldarg.2
0xb807  newobj   instance void Microsoft.ReportingServices.Diagnostics.ReqInfo::.ctor(string userName, string path)
0xb80c  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xb811  ret
0xb812  ldarg.0
0xb813  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Diagnostics.RunningRequests::get_RequestInfoProp()
0xb818  ldarg.2
0xb819  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xb81e  castclass Microsoft.ReportingServices.Diagnostics.ReqInfo
0xb823  ldarg.1
0xb824  callvirt instance bool Microsoft.ReportingServices.Diagnostics.ReqInfo::AddRequest(string userName)
0xb829  pop
0xb82a  ret
```
