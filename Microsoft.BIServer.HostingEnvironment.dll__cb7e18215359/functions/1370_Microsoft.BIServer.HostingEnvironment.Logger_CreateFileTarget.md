# Microsoft.BIServer.HostingEnvironment.Logger::CreateFileTarget

- ea: `0x1370`
- end: `0x13cd`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::CreateFileTarget`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1140`

## pseudocode

```c

```

## disassembly

```asm
0x1370  ldarg.0
0x1371  callvirt instance string [NLog]NLog.Logger::get_Name()
0x1376  ldstr    aFiletarget// ".fileTarget"
0x137b  call     string [mscorlib]System.String::Concat(string, string)
0x1380  stloc.0
0x1381  newobj   instance void [NLog]NLog.Targets.FileTarget::.ctor()
0x1386  dup
0x1387  ldloc.0
0x1388  callvirt instance void [NLog]NLog.Targets.Target::set_Name(string)
0x138d  dup
0x138e  ldc.i4.0
0x138f  callvirt instance void [NLog]NLog.Targets.FileTarget::set_ConcurrentWrites(bool)
0x1394  dup
0x1395  ldc.i4.0
0x1396  callvirt instance void [NLog]NLog.Targets.FileTarget::set_EnableFileDelete(bool)
0x139b  dup
0x139c  ldarg.1
0x139d  ldstr    aDailydate_0// "_${DailyDate}"
0x13a2  ldarg.2
0x13a3  call     string [mscorlib]System.String::Concat(string, string, string)
0x13a8  call     class [NLog]NLog.Layouts.Layout [NLog]NLog.Layouts.Layout::op_Implicit(string)
0x13ad  callvirt instance void [NLog]NLog.Targets.FileTarget::set_FileName(class [NLog]NLog.Layouts.Layout)
0x13b2  dup
0x13b3  ldarg.3
0x13b4  call     class [NLog]NLog.Layouts.Layout [NLog]NLog.Layouts.Layout::op_Implicit(string)
0x13b9  callvirt instance void [NLog]NLog.Targets.TargetWithLayout::set_Layout(class [NLog]NLog.Layouts.Layout)
0x13be  stloc.1
0x13bf  call     class [NLog]NLog.Config.LoggingConfiguration [NLog]NLog.LogManager::get_Configuration()
0x13c4  ldloc.0
0x13c5  ldloc.1
0x13c6  callvirt instance void [NLog]NLog.Config.LoggingConfiguration::AddTarget(string, class [NLog]NLog.Targets.Target)
0x13cb  ldloc.1
0x13cc  ret
```
