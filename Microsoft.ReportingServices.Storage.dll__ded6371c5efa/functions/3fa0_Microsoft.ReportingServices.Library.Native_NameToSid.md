# Microsoft.ReportingServices.Library.Native::NameToSid

- ea: `0x3fa0`
- end: `0x3ff0`
- name: `Microsoft.ReportingServices.Library.Native::NameToSid`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x6e10`

## callees

- `0x3fa0`
- `0x4020`

## pseudocode

```c

```

## disassembly

```asm
0x3fa0  ldarg.0
0x3fa1  brfalse.s loc_3FAB
0x3fa3  ldarg.0
0x3fa4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3fa9  brtrue.s loc_3FB2
0x3fab  ldarg.0
0x3fac  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownUserNameException::.ctor(string)
0x3fb1  throw
0x3fb2  ldnull
0x3fb3  stloc.0
0x3fb4  ldc.i4.0
0x3fb5  stloc.1
0x3fb6  ldnull
0x3fb7  stloc.2
0x3fb8  ldarg.0
0x3fb9  ldloca.s 1
0x3fbb  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SafeLocalFree Microsoft.ReportingServices.Library.Native::GetSid(string name, [out] int32& length)
0x3fc0  stloc.0
0x3fc1  ldloc.0
0x3fc2  brtrue.s loc_3FCB
0x3fc4  ldarg.0
0x3fc5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.UnknownUserNameException::.ctor(string)
0x3fca  throw
0x3fcb  ldloc.1
0x3fcc  newarr   [mscorlib]System.Byte
0x3fd1  stloc.2
0x3fd2  ldloc.0
0x3fd3  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x3fd8  ldloc.2
0x3fd9  ldc.i4.0
0x3fda  ldloc.1
0x3fdb  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x3fe0  ldloc.2
0x3fe1  stloc.3
0x3fe2  leave.s  loc_3FEE
0x3fe4  ldloc.0
0x3fe5  brfalse.s loc_3FED
0x3fe7  ldloc.0
0x3fe8  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x3fed  endfinally
0x3fee  ldloc.3
0x3fef  ret
```
