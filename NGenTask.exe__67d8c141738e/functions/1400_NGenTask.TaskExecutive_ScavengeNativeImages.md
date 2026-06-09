# NGenTask.TaskExecutive::ScavengeNativeImages

- ea: `0x1400`
- end: `0x155e`
- name: `NGenTask.TaskExecutive::ScavengeNativeImages`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x310`

## callees

- `0x1400`
- `0x25c0`
- `0x2610`
- `0x2c30`
- `0x2c60`
- `0x3d60`
- `0x3fd0`

## string_xrefs

- `0x1401`: `Uninstall list of unused native images ({0})`
- `0x14f9`: `uninstall "{0}" /noroot`
- `0x1540`: `Attempted to scavenge {0} native images.`

## pseudocode

```c

```

## disassembly

```asm
0x1400  ldc.i4.3
0x1401  ldstr    aUninstallListO// "Uninstall list of unused native images "...
0x1406  ldc.i4.1
0x1407  newarr   [mscorlib]System.Object
0x140c  dup
0x140d  ldc.i4.0
0x140e  ldarg.2
0x140f  stelem.ref
0x1410  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1415  ldc.i4.0
0x1416  stloc.0
0x1417  ldc.i4.0
0x1418  stloc.1
0x1419  ldarg.1
0x141a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerFileInfo> NGenTask.AppDataDirectoryWalker::WalkNIFiles()
0x141f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerFileInfo>::GetEnumerator()
0x1424  stloc.2
0x1425  br       loc_1528
0x142a  ldloc.2
0x142b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerFileInfo>::get_Current()
0x1430  stloc.3
0x1431  ldarg.0
0x1432  volatile.
0x1434  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x1439  brfalse.s loc_1443
0x143b  ldloc.1
0x143c  stloc.s  6
0x143e  leave    loc_155B
0x1443  ldloc.3
0x1444  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x1449  stloc.s  4
0x144b  ldarg.s  7
0x144d  brfalse.s loc_1467
0x144f  ldloc.s  4
0x1451  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1456  ldstr    aAux// ".aux"
0x145b  call     string [mscorlib]System.String::Concat(string, string)
0x1460  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x1465  stloc.s  4
0x1467  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x146c  ldloc.s  4
0x146e  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_LastAccessTimeUtc()
0x1473  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1478  stloc.s  5
0x147a  ldloc.s  4
0x147c  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_CreationTime()
0x1481  ldarg.0
0x1482  ldfld    valuetype [mscorlib]System.DateTime NGenTask.TaskExecutive::m_startTime
0x1487  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x148c  brfalse.s loc_1492
0x148e  ldloc.1
0x148f  ldc.i4.1
0x1490  add
0x1491  stloc.1
0x1492  leave.s  loc_14B9
0x1494  stloc.s  7
0x1496  ldc.i4.0
0x1497  ldloc.s  7
0x1499  ldstr    aErrorFindingAg// "Error finding age of native image {0}"
0x149e  ldc.i4.1
0x149f  newarr   [mscorlib]System.Object
0x14a4  dup
0x14a5  ldc.i4.0
0x14a6  ldloc.3
0x14a7  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x14ac  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x14b1  stelem.ref
0x14b2  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x14b7  leave.s  loc_1528
0x14b9  ldc.i4.3
0x14ba  ldstr    aNativeImage0Ag// "Native Image {0} : Age {1}"
0x14bf  ldc.i4.2
0x14c0  newarr   [mscorlib]System.Object
0x14c5  dup
0x14c6  ldc.i4.0
0x14c7  ldloc.3
0x14c8  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x14cd  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x14d2  stelem.ref
0x14d3  dup
0x14d4  ldc.i4.1
0x14d5  ldloca.s 5
0x14d7  call     instance float64 [mscorlib]System.TimeSpan::get_TotalDays()
0x14dc  box      [mscorlib]System.Double
0x14e1  stelem.ref
0x14e2  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x14e7  ldloca.s 5
0x14e9  call     instance float64 [mscorlib]System.TimeSpan::get_TotalDays()
0x14ee  ldarg.3
0x14ef  ble.un.s loc_1528
0x14f1  ldloc.0
0x14f2  ldc.i4.1
0x14f3  add
0x14f4  stloc.0
0x14f5  ldarg.s  4
0x14f7  brfalse.s loc_151F
0x14f9  ldstr    aUninstall0Noro// "uninstall \"{0}\" /noroot"
0x14fe  ldloc.3
0x14ff  callvirt instance class [mscorlib]System.IO.FileInfo NGenTask.ContainerFileInfo::get_LogFile()
0x1504  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1509  call     string [mscorlib]System.String::Format(string, object)
0x150e  stloc.s  8
0x1510  ldarg.0
0x1511  ldarg.s  5
0x1513  ldloc.s  8
0x1515  ldnull
0x1516  call     instance int32 NGenTask.TaskExecutive::RunNGenCommand(string ngenCommand, string arguments, string container)
0x151b  stloc.s  9
0x151d  br.s     loc_1528
0x151f  ldarg.0
0x1520  ldloc.3
0x1521  ldarg.s  6
0x1523  call     instance void NGenTask.TaskExecutive::UninstallNativeImagePerUser(class NGenTask.ContainerFileInfo niFile, string shortVersion)
0x1528  ldloc.2
0x1529  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x152e  brtrue   loc_142A
0x1533  leave.s  loc_153F
0x1535  ldloc.2
0x1536  brfalse.s loc_153E
0x1538  ldloc.2
0x1539  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x153e  endfinally
0x153f  ldc.i4.3
0x1540  ldstr    aAttemptedToSca// "Attempted to scavenge {0} native images"...
0x1545  ldc.i4.1
0x1546  newarr   [mscorlib]System.Object
0x154b  dup
0x154c  ldc.i4.0
0x154d  ldloc.0
0x154e  box      [mscorlib]System.Int32
0x1553  stelem.ref
0x1554  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1559  ldloc.1
0x155a  ret
0x155b  ldloc.s  6
0x155d  ret
```
