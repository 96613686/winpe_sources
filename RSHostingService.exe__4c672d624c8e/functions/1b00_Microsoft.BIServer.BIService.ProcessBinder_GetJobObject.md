# Microsoft.BIServer.BIService.ProcessBinder::GetJobObject

- ea: `0x1b00`
- end: `0x1ba3`
- name: `Microsoft.BIServer.BIService.ProcessBinder::GetJobObject`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bb0`

## callees

- `0x1ad0`
- `0x1b00`
- `0x25f0`
- `0x2640`
- `0x2650`

## pseudocode

```c

```

## disassembly

```asm
0x1b00  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1b05  ldnull
0x1b06  call     class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle Microsoft.BIServer.BIService.Win32::CreateJobObject(native int jobAttributes, string name)
0x1b0b  stloc.0
0x1b0c  ldloc.0
0x1b0d  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x1b12  brfalse.s loc_1B24
0x1b14  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1b19  ldstr    aUnableToInitia// "Unable to initialize monitoring of proc"...
0x1b1e  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32, string)
0x1b23  throw
0x1b24  ldloca.s 5
0x1b26  initobj  JobObjectBasicLimitInfo
0x1b2c  ldloca.s 5
0x1b2e  ldc.i4   0x2000
0x1b33  stfld    unsigned int32 JobObjectBasicLimitInfo::LimitFlags
0x1b38  ldloc.s  5
0x1b3a  stloc.1
0x1b3b  ldloca.s 6
0x1b3d  initobj  JobObjectExtendedLimitInfo
0x1b43  ldloca.s 6
0x1b45  ldloc.1
0x1b46  stfld    valuetype JobObjectBasicLimitInfo JobObjectExtendedLimitInfo::BasicLimitInfo
0x1b4b  ldloc.s  6
0x1b4d  ldtoken  JobObjectExtendedLimitInfo
0x1b52  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b57  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x1b5c  stloc.2
0x1b5d  ldloc.2
0x1b5e  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0x1b63  stloc.3
0x1b64  ldloc.3
0x1b65  ldc.i4.0
0x1b66  call     T0x2B000015
0x1b6b  ldloc.3
0x1b6c  ldc.i4.1
0x1b6d  newobj   instance void Microsoft.BIServer.BIService.SafeUnmanagedMemoryHandle::.ctor(native int preexistingHandle, bool ownsHandle)
0x1b72  stloc.s  4
0x1b74  ldloc.0
0x1b75  ldc.i4.s 9
0x1b77  ldloc.s  4
0x1b79  ldloc.2
0x1b7a  call     bool Microsoft.BIServer.BIService.Win32::SetInformationJobObject(class [mscorlib]System.Runtime.InteropServices.SafeHandle hJob, valuetype JobObjectInfoType infoType, class [mscorlib]System.Runtime.InteropServices.SafeHandle lpJobObjectInfo, unsigned int32 cbJobObjectInfoLength)
0x1b7f  brtrue.s loc_1B91
0x1b81  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1b86  ldstr    aUnableToSetInf// "Unable to set information"
0x1b8b  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32, string)
0x1b90  throw
0x1b91  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x1b96  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x1b9b  ldloc.0
0x1b9c  call     void Microsoft.BIServer.BIService.ProcessBinder::BindInternal(int32 processId, class [mscorlib]System.Runtime.InteropServices.SafeHandle jobObject)
0x1ba1  ldloc.0
0x1ba2  ret
```
