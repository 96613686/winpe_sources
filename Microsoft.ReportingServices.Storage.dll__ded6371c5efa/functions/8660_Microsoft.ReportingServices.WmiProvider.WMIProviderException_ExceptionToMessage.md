# Microsoft.ReportingServices.WmiProvider.WMIProviderException::ExceptionToMessage

- ea: `0x8660`
- end: `0x86a8`
- name: `Microsoft.ReportingServices.WmiProvider.WMIProviderException::ExceptionToMessage`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x8630`

## callees

- `0x8660`
- `0x8a10`
- `0x8e40`
- `0x8e50`

## pseudocode

```c

```

## disassembly

```asm
0x8660  ldarg.0
0x8661  isinst   [System.Management]System.Management.ManagementException
0x8666  brfalse.s loc_868E
0x8668  ldarg.0
0x8669  castclass [System.Management]System.Management.ManagementException
0x866e  callvirt instance valuetype [System.Management]System.Management.ManagementStatus [System.Management]System.Management.ManagementException::get_ErrorCode()
0x8673  stloc.0
0x8674  ldloc.0
0x8675  ldc.i4   0x80041003
0x867a  bne.un.s loc_8682
0x867c  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ManagementException_AccessDenied()
0x8681  ret
0x8682  ldarg.0
0x8683  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8688  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::ManagementException_Generic(string wmiError)
0x868d  ret
0x868e  ldarg.0
0x868f  isinst   [mscorlib]System.UnauthorizedAccessException
0x8694  brfalse.s loc_869C
0x8696  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::get_ManagementException_AccessDenied()
0x869b  ret
0x869c  ldarg.0
0x869d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x86a2  call     string Microsoft.ReportingServices.WmiProvider.WMIProviderExceptionStrings::Exception_Generic(string genericError)
0x86a7  ret
```
