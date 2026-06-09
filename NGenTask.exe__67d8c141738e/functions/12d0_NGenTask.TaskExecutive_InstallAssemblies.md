# NGenTask.TaskExecutive::InstallAssemblies

- ea: `0x12d0`
- end: `0x137d`
- name: `NGenTask.TaskExecutive::InstallAssemblies`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x310`

## callees

- `0x110`
- `0x12d0`
- `0x25c0`
- `0x2c30`
- `0x2df0`
- `0x3440`
- `0x3460`
- `0x3480`
- `0x3710`

## string_xrefs

- `0x12d1`: `Installing new NGEN images ({0})`
- `0x1312`: `Insufficient Disk space to run additional ngen install commands`

## pseudocode

```c

```

## disassembly

```asm
0x12d0  ldc.i4.3
0x12d1  ldstr    aInstallingNewN// "Installing new NGEN images ({0})"
0x12d6  ldc.i4.1
0x12d7  newarr   [mscorlib]System.Object
0x12dc  dup
0x12dd  ldc.i4.0
0x12de  ldarg.2
0x12df  stelem.ref
0x12e0  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x12e5  ldc.i4.0
0x12e6  stloc.0
0x12e7  ldarg.1
0x12e8  callvirt instance class [System]System.Collections.Generic.ISet`1<class NGenTask.ILAssembly> NGenTask.ParsedLogsInfo::get_ILAssemblies()
0x12ed  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ILAssembly>::GetEnumerator()
0x12f2  stloc.1
0x12f3  br.s     loc_1368
0x12f5  ldloc.1
0x12f6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ILAssembly>::get_Current()
0x12fb  stloc.2
0x12fc  ldarg.0
0x12fd  volatile.
0x12ff  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x1304  brfalse.s loc_1308
0x1306  leave.s  loc_137C
0x1308  ldarg.s  4
0x130a  call     bool NGenTask.TaskHelper::CheckFreeSpace(class [mscorlib]System.IO.DirectoryInfo niDirectory)
0x130f  brtrue.s loc_1324
0x1311  ldc.i4.1
0x1312  ldstr    aInsufficientDi// "Insufficient Disk space to run addition"...
0x1317  ldc.i4.0
0x1318  newarr   [mscorlib]System.Object
0x131d  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1322  leave.s  loc_137C
0x1324  ldloc.2
0x1325  callvirt instance string NGenTask.ILAssembly::get_NGenArgs()
0x132a  stloc.3
0x132b  ldloc.3
0x132c  ldstr    aVersion// " /version:"
0x1331  ldarg.2
0x1332  call     string [mscorlib]System.String::Concat(string, string, string)
0x1337  stloc.3
0x1338  ldarg.0
0x1339  ldarg.3
0x133a  ldloc.3
0x133b  ldloc.2
0x133c  callvirt instance string NGenTask.ILAssembly::get_Container()
0x1341  call     instance int32 NGenTask.TaskExecutive::RunNGenCommand(string ngenCommand, string arguments, string container)
0x1346  stloc.s  4
0x1348  ldloc.s  4
0x134a  ldc.i4.m1
0x134b  bne.un.s loc_135A
0x134d  ldarg.s  5
0x134f  ldloc.2
0x1350  callvirt instance string NGenTask.ILAssembly::get_AssemblyName()
0x1355  callvirt instance void NGenTask.ExcludeList::Add(string assembly)
0x135a  ldloc.0
0x135b  ldc.i4.1
0x135c  add
0x135d  dup
0x135e  stloc.0
0x135f  ldc.i4   0x1F4
0x1364  blt.s    loc_1368
0x1366  leave.s  loc_137C
0x1368  ldloc.1
0x1369  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x136e  brtrue.s loc_12F5
0x1370  leave.s  loc_137C
0x1372  ldloc.1
0x1373  brfalse.s loc_137B
0x1375  ldloc.1
0x1376  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x137b  endfinally
0x137c  ret
```
