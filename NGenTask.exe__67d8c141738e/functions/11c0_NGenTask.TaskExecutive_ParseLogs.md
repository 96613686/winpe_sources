# NGenTask.TaskExecutive::ParseLogs

- ea: `0x11c0`
- end: `0x12c8`
- name: `NGenTask.TaskExecutive::ParseLogs`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x11c0`
- `0x2c30`
- `0x2c60`
- `0x3560`
- `0x3620`
- `0x3790`
- `0x3e00`
- `0x3ef0`
- `0x3fc0`

## string_xrefs

- `0x1247`: `Unable to locate local native image directory`

## pseudocode

```c

```

## disassembly

```asm
0x11c0  ldc.i4.3
0x11c1  ldstr    aParsingLogs0// "Parsing Logs ({0})"
0x11c6  ldc.i4.1
0x11c7  newarr   [mscorlib]System.Object
0x11cc  dup
0x11cd  ldc.i4.0
0x11ce  ldarg.2
0x11cf  stelem.ref
0x11d0  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x11d5  newobj   instance void NGenTask.ParsedLogsInfo::.ctor()
0x11da  stloc.0
0x11db  ldarg.1
0x11dc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo> NGenTask.AppDataDirectoryWalker::GetLogDirectories()
0x11e1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo>::GetEnumerator()
0x11e6  stloc.1
0x11e7  br       loc_12AC
0x11ec  ldloc.1
0x11ed  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo>::get_Current()
0x11f2  stloc.2
0x11f3  ldarg.0
0x11f4  volatile.
0x11f6  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x11fb  brfalse.s loc_1205
0x11fd  ldnull
0x11fe  stloc.s  5
0x1200  leave    loc_12C5
0x1205  ldarg.0
0x1206  ldloc.2
0x1207  ldarg.s  4
0x1209  newobj   instance void NGenTask.LogWalker::.ctor(class NGenTask.TaskExecutive task, class NGenTask.ContainerDirectoryInfo logDirectory, float64 logsScavengeThreshold)
0x120e  stloc.3
0x120f  ldarg.s  6
0x1211  brfalse.s loc_1223
0x1213  ldarg.s  6
0x1215  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x121a  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x121f  stloc.s  4
0x1221  br.s     loc_1259
0x1223  nop
0x1224  ldloc.2
0x1225  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x122a  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x122f  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1234  ldstr    aNativeimages_0// "NativeImages"
0x1239  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x123e  stloc.s  4
0x1240  leave.s  loc_1259
0x1242  stloc.s  6
0x1244  ldc.i4.0
0x1245  ldloc.s  6
0x1247  ldstr    aUnableToLocate// "Unable to locate local native image dir"...
0x124c  ldc.i4.0
0x124d  newarr   [mscorlib]System.Object
0x1252  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x1257  leave.s  loc_12AC
0x1259  ldc.i4.3
0x125a  ldstr    aParsing// "Parsing: "
0x125f  ldloc.2
0x1260  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x1265  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x126a  call     string [mscorlib]System.String::Concat(string, string)
0x126f  ldc.i4.0
0x1270  newarr   [mscorlib]System.Object
0x1275  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x127a  ldarg.3
0x127b  ldloc.3
0x127c  ldarg.s  5
0x127e  ldloc.s  4
0x1280  ldarg.s  7
0x1282  ldarg.s  8
0x1284  callvirt instance class NGenTask.ParsedLogsInfo NGenTask.LogsParser::ParseLogs(class NGenTask.LogWalker logWalk, bool frameworkAssemblyOnly, string niDirectory, valuetype [mscorlib]System.DateTime fxUpdateTime, class NGenTask.ExcludeList excludeList)
0x1289  stloc.s  7
0x128b  ldloc.0
0x128c  ldloc.s  7
0x128e  callvirt instance void NGenTask.ParsedLogsInfo::AppendParsedLog(class NGenTask.ParsedLogsInfo plinfo)
0x1293  leave.s  loc_12AC
0x1295  stloc.s  8
0x1297  ldc.i4.0
0x1298  ldloc.s  8
0x129a  ldstr    aErrorParsingLo// "Error parsing logs"
0x129f  ldc.i4.0
0x12a0  newarr   [mscorlib]System.Object
0x12a5  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x12aa  leave.s  loc_12AC
0x12ac  ldloc.1
0x12ad  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x12b2  brtrue   loc_11EC
0x12b7  leave.s  loc_12C3
0x12b9  ldloc.1
0x12ba  brfalse.s loc_12C2
0x12bc  ldloc.1
0x12bd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12c2  endfinally
0x12c3  ldloc.0
0x12c4  ret
0x12c5  ldloc.s  5
0x12c7  ret
```
