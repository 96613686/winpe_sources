# NGenTask.TaskExecutive::NgenClientLockListener

- ea: `0x19f0`
- end: `0x1ac8`
- name: `NGenTask.TaskExecutive::NgenClientLockListener`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1080`
- `0x19f0`
- `0x2c30`
- `0x2c60`
- `0x31c0`

## string_xrefs

- `0x1a0b`: `GetSystemWindowsDirectory failed`
- `0x1a22`: `Microsoft.Net\ngenserviceclientlock.dat`
- `0x1a57`: `Remove machine-wide lock file failed`
- `0x1a85`: `Task was interrupted by Ngen client`
- `0x1aa7`: `Task resuming after Ngen client interruption`

## pseudocode

```c

```

## disassembly

```asm
0x19f0  ldc.i4   0x104
0x19f5  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x19fa  stloc.0
0x19fb  ldloc.0
0x19fc  ldc.i4   0x104
0x1a01  call     int32 NGenTask.Win32Native::GetSystemWindowsDirectory(class [mscorlib]System.Text.StringBuilder sb, int32 length)
0x1a06  stloc.1
0x1a07  ldloc.1
0x1a08  brtrue.s loc_1A1C
0x1a0a  ldc.i4.0
0x1a0b  ldstr    aGetsystemwindo// "GetSystemWindowsDirectory failed"
0x1a10  ldc.i4.0
0x1a11  newarr   [mscorlib]System.Object
0x1a16  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1a1b  ret
0x1a1c  ldloc.0
0x1a1d  callvirt instance string [mscorlib]System.Object::ToString()
0x1a22  ldstr    aMicrosoftNetNg// "Microsoft.Net\\ngenserviceclientlock.da"...
0x1a27  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1a2c  stloc.2
0x1a2d  ldc.i4.m1
0x1a2e  stloc.3
0x1a2f  ldc.i4   0x3E8
0x1a34  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x1a39  ldc.i4.0
0x1a3a  stloc.s  4
0x1a3c  ldloc.2
0x1a3d  call     bool [mscorlib]System.IO.File::Exists(string)
0x1a42  brfalse.s loc_1A6C
0x1a44  ldloc.2
0x1a45  call     void [mscorlib]System.IO.File::Delete(string)
0x1a4a  leave.s  loc_1A6C
0x1a4c  pop
0x1a4d  ldc.i4.1
0x1a4e  stloc.s  4
0x1a50  leave.s  loc_1A6C
0x1a52  stloc.s  5
0x1a54  ldc.i4.0
0x1a55  ldloc.s  5
0x1a57  ldstr    aRemoveMachineW// "Remove machine-wide lock file failed"
0x1a5c  ldc.i4.0
0x1a5d  newarr   [mscorlib]System.Object
0x1a62  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x1a67  ldc.i4.1
0x1a68  stloc.s  4
0x1a6a  leave.s  loc_1A6C
0x1a6c  ldloc.s  4
0x1a6e  brtrue.s loc_1A78
0x1a70  ldloc.3
0x1a71  ldc.i4.0
0x1a72  blt.s    loc_1A78
0x1a74  ldloc.3
0x1a75  ldc.i4.1
0x1a76  sub
0x1a77  stloc.3
0x1a78  ldloc.s  4
0x1a7a  brtrue.s loc_1A80
0x1a7c  ldloc.3
0x1a7d  ldc.i4.0
0x1a7e  ble.s    loc_1AA3
0x1a80  ldloc.3
0x1a81  ldc.i4.m1
0x1a82  bne.un.s loc_1A95
0x1a84  ldc.i4.m1
0x1a85  ldstr    aTaskWasInterru_0// "Task was interrupted by Ngen client"
0x1a8a  ldc.i4.0
0x1a8b  newarr   [mscorlib]System.Object
0x1a90  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1a95  ldloc.s  4
0x1a97  brfalse.s loc_1A9B
0x1a99  ldc.i4.5
0x1a9a  stloc.3
0x1a9b  ldarg.0
0x1a9c  call     instance void NGenTask.TaskExecutive::NgenClientInterruptStop()
0x1aa1  br.s     loc_1A2F
0x1aa3  ldloc.3
0x1aa4  brtrue.s loc_1A2F
0x1aa6  ldc.i4.m1
0x1aa7  ldstr    aTaskResumingAf// "Task resuming after Ngen client interru"...
0x1aac  ldc.i4.0
0x1aad  newarr   [mscorlib]System.Object
0x1ab2  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1ab7  ldarg.0
0x1ab8  ldfld    class [mscorlib]System.Threading.AutoResetEvent NGenTask.TaskExecutive::m_ngenInterruptFinishedEvent
0x1abd  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x1ac2  pop
0x1ac3  br       loc_1A2F
```
