# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::GetDomainTokenHandle

- ea: `0x1c20`
- end: `0x1c42`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareProvider::GetDomainTokenHandle`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b70`

## pseudocode

```c

```

## disassembly

```asm
0x1c20  ldarg.3
0x1c21  ldnull
0x1c22  stind.ref
0x1c23  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1c28  pop
0x1c29  ldarg.3
0x1c2a  ldnull
0x1c2b  ldc.i4.0
0x1c2c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c31  ldarg.1
0x1c32  ldarg.0
0x1c33  ldarg.2
0x1c34  call     class [ReportingServicesNativeClient]Util.SafeToken [ReportingServicesNativeClient]RSRemoteRpcClient.RemoteLogon::GetRemoteImpToken(string, int32, valuetype [mscorlib]System.Guid, string, string, string)
0x1c39  stind.ref
0x1c3a  ldarg.3
0x1c3b  ldind.ref
0x1c3c  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x1c41  ret
```
