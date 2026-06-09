# NGenTask.TaskHelper::CheckFreeSpace

- ea: `0x2df0`
- end: `0x2e95`
- name: `NGenTask.TaskHelper::CheckFreeSpace`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x310`
- `0x12d0`

## callees

- `0x2c30`
- `0x2c60`
- `0x2df0`

## pseudocode

```c

```

## disassembly

```asm
0x2df0  ldarg.0
0x2df1  brtrue.s loc_2DF5
0x2df3  ldc.i4.1
0x2df4  ret
0x2df5  nop
0x2df6  ldarg.0
0x2df7  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x2dfc  newobj   instance void [mscorlib]System.IO.DriveInfo::.ctor(string)
0x2e01  stloc.0
0x2e02  ldloc.0
0x2e03  callvirt instance int64 [mscorlib]System.IO.DriveInfo::get_AvailableFreeSpace()
0x2e08  stloc.1
0x2e09  ldloc.0
0x2e0a  callvirt instance int64 [mscorlib]System.IO.DriveInfo::get_TotalSize()
0x2e0f  stloc.2
0x2e10  ldloc.1
0x2e11  ldc.i4   0x6400000
0x2e16  conv.i8
0x2e17  ble.s    loc_2E29
0x2e19  ldloc.1
0x2e1a  conv.r8
0x2e1b  ldloc.2
0x2e1c  conv.r8
0x2e1d  div
0x2e1e  ldc.r8   0.1
0x2e27  bgt.un.s loc_2E78
0x2e29  ldc.i4.0
0x2e2a  ldstr    aNotCreatingNew// "Not creating new native images due to d"...
0x2e2f  ldc.i4.0
0x2e30  newarr   [mscorlib]System.Object
0x2e35  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2e3a  ldc.i4.3
0x2e3b  ldstr    a0MbAvailableOu// "({0} MB available out of {1} MB) on {2}"
0x2e40  ldc.i4.3
0x2e41  newarr   [mscorlib]System.Object
0x2e46  dup
0x2e47  ldc.i4.0
0x2e48  ldloc.1
0x2e49  ldc.i4   0x100000
0x2e4e  conv.i8
0x2e4f  div
0x2e50  box      [mscorlib]System.Int64
0x2e55  stelem.ref
0x2e56  dup
0x2e57  ldc.i4.1
0x2e58  ldloc.2
0x2e59  ldc.i4   0x100000
0x2e5e  conv.i8
0x2e5f  div
0x2e60  box      [mscorlib]System.Int64
0x2e65  stelem.ref
0x2e66  dup
0x2e67  ldc.i4.2
0x2e68  ldloc.0
0x2e69  callvirt instance string [mscorlib]System.IO.DriveInfo::get_Name()
0x2e6e  stelem.ref
0x2e6f  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2e74  ldc.i4.0
0x2e75  stloc.3
0x2e76  leave.s  loc_2E93
0x2e78  leave.s  loc_2E91
0x2e7a  stloc.s  4
0x2e7c  ldc.i4.0
0x2e7d  ldloc.s  4
0x2e7f  ldstr    aUnableToCheckD// "Unable to check disk free space"
0x2e84  ldc.i4.0
0x2e85  newarr   [mscorlib]System.Object
0x2e8a  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2e8f  leave.s  loc_2E91
0x2e91  ldc.i4.1
0x2e92  ret
0x2e93  ldloc.3
0x2e94  ret
```
