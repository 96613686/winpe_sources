# NGenTask.LogsParser::ScavengeLogs

- ea: `0x3830`
- end: `0x3923`
- name: `NGenTask.LogsParser::ScavengeLogs`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1120`

## callees

- `0x2c30`
- `0x2c60`
- `0x3830`
- `0x3d60`
- `0x3e00`
- `0x3f20`
- `0x3f30`

## string_xrefs

- `0x3899`: `Attempted to scavenge {0} logs.`
- `0x38e0`: `Exception while removing log directory`

## pseudocode

```c

```

## disassembly

```asm
0x3830  ldc.i4.0
0x3831  stloc.0
0x3832  ldarg.1
0x3833  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerFileInfo> NGenTask.LogWalker::WalkOldLogs()
0x3838  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerFileInfo>::GetEnumerator()
0x383d  stloc.1
0x383e  br.s     loc_3884
0x3840  ldloc.1
0x3841  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerFileInfo>::get_Current()
0x3846  stloc.2
0x3847  ldloc.0
0x3848  ldc.i4.1
0x3849  add
0x384a  stloc.0
0x384b  ldloc.2
0x384c  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x3851  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0x3856  leave.s  loc_3884
0x3858  stloc.3
0x3859  ldc.i4.0
0x385a  ldloc.3
0x385b  ldstr    aExceptionWhile_1// "Exception while scavenging log file"
0x3860  ldc.i4.0
0x3861  newarr   [mscorlib]System.Object
0x3866  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x386b  leave.s  loc_3884
0x386d  stloc.s  4
0x386f  ldc.i4.0
0x3870  ldloc.s  4
0x3872  ldstr    aExceptionWhile_1// "Exception while scavenging log file"
0x3877  ldc.i4.0
0x3878  newarr   [mscorlib]System.Object
0x387d  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x3882  leave.s  loc_3884
0x3884  ldloc.1
0x3885  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x388a  brtrue.s loc_3840
0x388c  leave.s  loc_3898
0x388e  ldloc.1
0x388f  brfalse.s loc_3897
0x3891  ldloc.1
0x3892  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3897  endfinally
0x3898  ldc.i4.3
0x3899  ldstr    aAttemptedToSca_0// "Attempted to scavenge {0} logs."
0x389e  ldc.i4.1
0x389f  newarr   [mscorlib]System.Object
0x38a4  dup
0x38a5  ldc.i4.0
0x38a6  ldloc.0
0x38a7  box      [mscorlib]System.Int32
0x38ac  stelem.ref
0x38ad  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x38b2  ldarg.1
0x38b3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo> NGenTask.LogWalker::WalkLogDirectories()
0x38b8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo>::GetEnumerator()
0x38bd  stloc.s  5
0x38bf  br.s     loc_38F2
0x38c1  ldloc.s  5
0x38c3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo>::get_Current()
0x38c8  stloc.s  6
0x38ca  ldloc.s  6
0x38cc  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x38d1  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0x38d6  leave.s  loc_38F2
0x38d8  pop
0x38d9  leave.s  loc_38F2
0x38db  stloc.s  7
0x38dd  ldc.i4.0
0x38de  ldloc.s  7
0x38e0  ldstr    aExceptionWhile_2// "Exception while removing log directory"
0x38e5  ldc.i4.0
0x38e6  newarr   [mscorlib]System.Object
0x38eb  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x38f0  leave.s  loc_38F2
0x38f2  ldloc.s  5
0x38f4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x38f9  brtrue.s loc_38C1
0x38fb  leave.s  loc_3909
0x38fd  ldloc.s  5
0x38ff  brfalse.s loc_3908
0x3901  ldloc.s  5
0x3903  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3908  endfinally
0x3909  leave.s  loc_3922
0x390b  stloc.s  8
0x390d  ldc.i4.0
0x390e  ldloc.s  8
0x3910  ldstr    aExceptionWhile_3// "Exception while walking log files for s"...
0x3915  ldc.i4.0
0x3916  newarr   [mscorlib]System.Object
0x391b  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x3920  leave.s  loc_3922
0x3922  ret
```
