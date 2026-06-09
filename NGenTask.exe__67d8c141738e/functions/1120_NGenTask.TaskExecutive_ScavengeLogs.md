# NGenTask.TaskExecutive::ScavengeLogs

- ea: `0x1120`
- end: `0x11b4`
- name: `NGenTask.TaskExecutive::ScavengeLogs`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x1120`
- `0x2c30`
- `0x2c60`
- `0x3830`
- `0x3e00`
- `0x3ef0`
- `0x3fc0`

## pseudocode

```c

```

## disassembly

```asm
0x1120  ldc.i4.3
0x1121  ldstr    aScavengingLogs// "Scavenging Logs ({0})"
0x1126  ldc.i4.1
0x1127  newarr   [mscorlib]System.Object
0x112c  dup
0x112d  ldc.i4.0
0x112e  ldarg.2
0x112f  stelem.ref
0x1130  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1135  ldarg.1
0x1136  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo> NGenTask.AppDataDirectoryWalker::GetLogDirectories()
0x113b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo>::GetEnumerator()
0x1140  stloc.0
0x1141  br.s     loc_119F
0x1143  ldloc.0
0x1144  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo>::get_Current()
0x1149  stloc.1
0x114a  ldarg.0
0x114b  volatile.
0x114d  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x1152  brfalse.s loc_1156
0x1154  leave.s  loc_11B3
0x1156  ldarg.0
0x1157  ldloc.1
0x1158  ldarg.s  4
0x115a  newobj   instance void NGenTask.LogWalker::.ctor(class NGenTask.TaskExecutive task, class NGenTask.ContainerDirectoryInfo logDirectory, float64 logsScavengeThreshold)
0x115f  stloc.2
0x1160  ldc.i4.3
0x1161  ldstr    aScavenging// "Scavenging: "
0x1166  ldloc.1
0x1167  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x116c  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1171  call     string [mscorlib]System.String::Concat(string, string)
0x1176  ldc.i4.0
0x1177  newarr   [mscorlib]System.Object
0x117c  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1181  ldarg.3
0x1182  ldloc.2
0x1183  callvirt instance void NGenTask.LogsParser::ScavengeLogs(class NGenTask.LogWalker logWalk)
0x1188  leave.s  loc_119F
0x118a  stloc.3
0x118b  ldc.i4.0
0x118c  ldloc.3
0x118d  ldstr    aErrorScavengin// "Error scavenging logs"
0x1192  ldc.i4.0
0x1193  newarr   [mscorlib]System.Object
0x1198  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x119d  leave.s  loc_119F
0x119f  ldloc.0
0x11a0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11a5  brtrue.s loc_1143
0x11a7  leave.s  loc_11B3
0x11a9  ldloc.0
0x11aa  brfalse.s loc_11B2
0x11ac  ldloc.0
0x11ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11b2  endfinally
0x11b3  ret
```
