# NGenTask.LogsParser::ParseLogs

- ea: `0x3790`
- end: `0x382a`
- name: `NGenTask.LogsParser::ParseLogs`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x11c0`

## callees

- `0x2c30`
- `0x2c60`
- `0x3560`
- `0x3620`
- `0x3790`
- `0x3930`
- `0x3f40`

## pseudocode

```c

```

## disassembly

```asm
0x3790  newobj   instance void NGenTask.ParsedLogsInfo::.ctor()
0x3795  stloc.0
0x3796  ldc.i4.0
0x3797  stloc.1
0x3798  ldarg.1
0x3799  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerFileInfo> NGenTask.LogWalker::WalkLogs()
0x379e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerFileInfo>::GetEnumerator()
0x37a3  stloc.2
0x37a4  br.s     loc_37E1
0x37a6  ldloc.2
0x37a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerFileInfo>::get_Current()
0x37ac  stloc.3
0x37ad  ldloc.1
0x37ae  ldc.i4.1
0x37af  add
0x37b0  stloc.1
0x37b1  ldarg.0
0x37b2  ldloc.3
0x37b3  ldarg.2
0x37b4  ldarg.3
0x37b5  ldarg.s  4
0x37b7  ldarg.s  5
0x37b9  call     instance class NGenTask.ParsedLogsInfo NGenTask.LogsParser::ParseLog(class NGenTask.ContainerFileInfo finfoLog, bool frameworkAssemblyOnly, string niDirectory, valuetype [mscorlib]System.DateTime fxUpdateTime, class NGenTask.ExcludeList excludeList)
0x37be  stloc.s  4
0x37c0  ldloc.0
0x37c1  ldloc.s  4
0x37c3  callvirt instance void NGenTask.ParsedLogsInfo::AppendParsedLog(class NGenTask.ParsedLogsInfo plinfo)
0x37c8  leave.s  loc_37E1
0x37ca  stloc.s  5
0x37cc  ldc.i4.0
0x37cd  ldloc.s  5
0x37cf  ldstr    aExceptionWhile// "Exception while parsing log"
0x37d4  ldc.i4.0
0x37d5  newarr   [mscorlib]System.Object
0x37da  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x37df  leave.s  loc_37E1
0x37e1  ldloc.2
0x37e2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x37e7  brtrue.s loc_37A6
0x37e9  leave.s  loc_37F5
0x37eb  ldloc.2
0x37ec  brfalse.s loc_37F4
0x37ee  ldloc.2
0x37ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37f4  endfinally
0x37f5  ldc.i4.3
0x37f6  ldstr    aParsed0Logs// "Parsed {0} logs."
0x37fb  ldc.i4.1
0x37fc  newarr   [mscorlib]System.Object
0x3801  dup
0x3802  ldc.i4.0
0x3803  ldloc.1
0x3804  box      [mscorlib]System.Int32
0x3809  stelem.ref
0x380a  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x380f  leave.s  loc_3828
0x3811  stloc.s  6
0x3813  ldc.i4.0
0x3814  ldloc.s  6
0x3816  ldstr    aExceptionWhile_0// "Exception while walking log files for p"...
0x381b  ldc.i4.0
0x381c  newarr   [mscorlib]System.Object
0x3821  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x3826  leave.s  loc_3828
0x3828  ldloc.0
0x3829  ret
```
