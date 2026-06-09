# Microsoft.BIServer.HostingEnvironment.Logger::CreateTest

- ea: `0xea0`
- end: `0xf0a`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::CreateTest`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xe80`
- `0x1550`

## string_xrefs

- `0xeef`: `Memory Logger created: level {0}`

## pseudocode

```c

```

## disassembly

```asm
0xea0  ldarg.0
0xea1  call     class [NLog]NLog.LogLevel Microsoft.BIServer.HostingEnvironment.Logger::Convert(valuetype Level level)
0xea6  stloc.0
0xea7  newobj   instance void [NLog]NLog.Targets.MemoryTarget::.ctor()
0xeac  stloc.1
0xead  call     class [NLog]NLog.Config.LoggingConfiguration [NLog]NLog.LogManager::get_Configuration()
0xeb2  ldstr    aMemory// "memory"
0xeb7  ldloc.1
0xeb8  callvirt instance void [NLog]NLog.Config.LoggingConfiguration::AddTarget(string, class [NLog]NLog.Targets.Target)
0xebd  ldloc.1
0xebe  ldstr    aLevelUppercase// "${level:uppercase=true}|${message}${exc"...
0xec3  call     class [NLog]NLog.Layouts.Layout [NLog]NLog.Layouts.Layout::op_Implicit(string)
0xec8  callvirt instance void [NLog]NLog.Targets.TargetWithLayout::set_Layout(class [NLog]NLog.Layouts.Layout)
0xecd  ldstr    aEventlog// "eventLog"
0xed2  ldloc.0
0xed3  ldloc.1
0xed4  newobj   instance void [NLog]NLog.Config.LoggingRule::.ctor(string, class [NLog]NLog.LogLevel, class [NLog]NLog.Targets.Target)
0xed9  stloc.2
0xeda  call     class [NLog]NLog.Config.LoggingConfiguration [NLog]NLog.LogManager::get_Configuration()
0xedf  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [NLog]NLog.Config.LoggingRule> [NLog]NLog.Config.LoggingConfiguration::get_LoggingRules()
0xee4  ldloc.2
0xee5  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [NLog]NLog.Config.LoggingRule>::Add(var<u1>)
0xeea  call     void [NLog]NLog.LogManager::ReconfigExistingLoggers()
0xeef  ldstr    aMemoryLoggerCr// "Memory Logger created: level {0}"
0xef4  ldc.i4.1
0xef5  newarr   [mscorlib]System.Object
0xefa  dup
0xefb  ldc.i4.0
0xefc  ldarg.0
0xefd  box      Level
0xf02  stelem.ref
0xf03  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0xf08  ldloc.1
0xf09  ret
```
