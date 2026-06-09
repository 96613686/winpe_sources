# NGenTask.TaskExecutive::OptimizeUsedBinaries

- ea: `0x1f20`
- end: `0x1f8f`
- name: `NGenTask.TaskExecutive::OptimizeUsedBinaries`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x1f20`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x1f20  ldstr    aSoftwareMicros// "Software\\Microsoft\\.NETFramework\\NGe"...
0x1f25  ldarg.0
0x1f26  call     string [mscorlib]System.String::Concat(string, string)
0x1f2b  stloc.0
0x1f2c  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x1f31  ldloc.0
0x1f32  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x1f37  stloc.1
0x1f38  ldloc.1
0x1f39  brtrue.s loc_1F3F
0x1f3b  ldarg.1
0x1f3c  stloc.3
0x1f3d  leave.s  loc_1F8D
0x1f3f  ldloc.1
0x1f40  ldstr    aOptimizeusedbi// "OptimizeUsedBinaries"
0x1f45  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x1f4a  stloc.2
0x1f4b  ldloc.2
0x1f4c  brfalse.s loc_1F56
0x1f4e  ldloc.2
0x1f4f  isinst   [mscorlib]System.Int32
0x1f54  brtrue.s loc_1F5A
0x1f56  ldarg.1
0x1f57  stloc.3
0x1f58  leave.s  loc_1F8D
0x1f5a  ldloc.2
0x1f5b  unbox.any [mscorlib]System.Int32
0x1f60  ldc.i4.0
0x1f61  cgt.un
0x1f63  stloc.3
0x1f64  leave.s  loc_1F8D
0x1f66  ldloc.1
0x1f67  brfalse.s loc_1F6F
0x1f69  ldloc.1
0x1f6a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f6f  endfinally
0x1f70  stloc.s  4
0x1f72  ldc.i4.0
0x1f73  ldloc.s  4
0x1f75  ldstr    aErrorDetermini// "Error determining OptimizeUsedBinaries "...
0x1f7a  ldc.i4.1
0x1f7b  newarr   [mscorlib]System.Object
0x1f80  dup
0x1f81  ldc.i4.0
0x1f82  ldarg.0
0x1f83  stelem.ref
0x1f84  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x1f89  ldarg.1
0x1f8a  stloc.3
0x1f8b  leave.s  loc_1F8D
0x1f8d  ldloc.3
0x1f8e  ret
```
