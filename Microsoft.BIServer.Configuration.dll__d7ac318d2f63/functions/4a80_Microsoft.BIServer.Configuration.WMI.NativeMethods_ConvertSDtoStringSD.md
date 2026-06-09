# Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertSDtoStringSD

- ea: `0x4a80`
- end: `0x4aa3`
- name: `Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertSDtoStringSD`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5280`

## callees

- `0x4a80`
- `0x4ab0`

## pseudocode

```c

```

## disassembly

```asm
0x4a80  ldarg.0
0x4a81  ldc.i4.1
0x4a82  ldc.i4.s 0xF
0x4a84  ldarg.1
0x4a85  ldarg.2
0x4a86  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertSecurityDescriptorToStringSecurityDescriptor([in] unsigned int8[] SecurityDescriptor, [in] int32 RequestedStringSDRevision, [in] valuetype SecurityInformation SecurityInformation, [out] native int& StringSecurityDescriptor, [out] int32& StringSecurityDescriptorLen)
0x4a8b  brtrue.s loc_4AA2
0x4a8d  ldstr    aFailToConvertS// "Fail to convert SD to string SD:"
0x4a92  call     void [mscorlib]System.Console::WriteLine(string)
0x4a97  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4a9c  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x4aa1  throw
0x4aa2  ret
```
