# Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertSDtoStringSD_0

- ea: `0x4b20`
- end: `0x4b49`
- name: `Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertSDtoStringSD_0`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5c30`

## callees

- `0x4b20`
- `0x4b50`

## pseudocode

```c

```

## disassembly

```asm
0x4b20  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4b25  stloc.0
0x4b26  ldc.i4.0
0x4b27  stloc.1
0x4b28  ldarg.0
0x4b29  ldc.i4.1
0x4b2a  ldc.i4.s 0xF
0x4b2c  ldloca.s 0
0x4b2e  ldloca.s 1
0x4b30  call     bool Microsoft.BIServer.Configuration.WMI.NativeMethods::ConvertSecurityDescriptorToStringSecurityDescriptor([in] native int pSecurityDescriptor, [in] int32 RequestedStringSDRevision, [in] valuetype SecurityInformation SecurityInformation, [out] native int& StringSecurityDescriptor, [out] int32& StringSecurityDescriptorLen)
0x4b35  brtrue.s loc_4B42
0x4b37  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x4b3c  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32)
0x4b41  throw
0x4b42  ldloc.0
0x4b43  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x4b48  ret
```
