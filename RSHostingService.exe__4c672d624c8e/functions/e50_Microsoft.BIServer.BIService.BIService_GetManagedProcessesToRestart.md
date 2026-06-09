# Microsoft.BIServer.BIService.BIService::GetManagedProcessesToRestart

- ea: `0xe50`
- end: `0xf23`
- name: `Microsoft.BIServer.BIService.BIService::GetManagedProcessesToRestart`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3110`

## callees

- `0xe50`
- `0xf30`
- `0x20d0`
- `0x2190`
- `0x2320`
- `0x31f0`

## string_xrefs

- `0xecc`: `Configuration of process '{0}' has changed. Values modified: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xe50  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xe55  stloc.0
0xe56  ldarg.0
0xe57  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses()
0xe5c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.BIServer.BIService.ProcessConfig>::GetEnumerator()
0xe61  stloc.1
0xe62  br       loc_F0A
0xe67  newobj   instance void <>c__DisplayClass38_0::.ctor()
0xe6c  stloc.2
0xe6d  ldloc.2
0xe6e  ldloc.1
0xe6f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.BIServer.BIService.ProcessConfig>::get_Current()
0xe74  stfld    class Microsoft.BIServer.BIService.ProcessConfig <>c__DisplayClass38_0::currentProcess
0xe79  ldarg.1
0xe7a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses()
0xe7f  ldloc.2
0xe80  ldftn    instance bool <>c__DisplayClass38_0::<GetManagedProcessesToRestart>b__0(class Microsoft.BIServer.BIService.ProcessConfig p)
0xe86  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.BIServer.BIService.ProcessConfig, bool>::.ctor(object, native int)
0xe8b  call     T0x2B00000A
0xe90  stloc.3
0xe91  ldloc.2
0xe92  ldfld    class Microsoft.BIServer.BIService.ProcessConfig <>c__DisplayClass38_0::currentProcess
0xe97  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0xe9c  ldloc.3
0xe9d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0xea2  call     T0x2B00000B
0xea7  stloc.s  4
0xea9  ldloc.2
0xeaa  ldfld    class Microsoft.BIServer.BIService.ProcessConfig <>c__DisplayClass38_0::currentProcess
0xeaf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0xeb4  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.BIServer.BIService.BIService::GetListOfConfigurationSettingsToRestartOn(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> config)
0xeb9  ldloc.s  4
0xebb  call     T0x2B00000C
0xec0  stloc.s  5
0xec2  ldloc.s  5
0xec4  call     T0x2B00000D
0xec9  ldc.i4.0
0xeca  ble.s    loc_F0A
0xecc  ldstr    aConfigurationO// "Configuration of process '{0}' has chan"...
0xed1  ldc.i4.2
0xed2  newarr   [mscorlib]System.Object
0xed7  dup
0xed8  ldc.i4.0
0xed9  ldloc.2
0xeda  ldfld    class Microsoft.BIServer.BIService.ProcessConfig <>c__DisplayClass38_0::currentProcess
0xedf  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0xee4  stelem.ref
0xee5  dup
0xee6  ldc.i4.1
0xee7  ldstr    asc_5BA6// ", "
0xeec  ldloc.s  5
0xeee  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xef3  stelem.ref
0xef4  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0xef9  ldloc.0
0xefa  ldloc.2
0xefb  ldfld    class Microsoft.BIServer.BIService.ProcessConfig <>c__DisplayClass38_0::currentProcess
0xf00  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Name()
0xf05  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xf0a  ldloc.1
0xf0b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf10  brtrue   loc_E67
0xf15  leave.s  loc_F21
0xf17  ldloc.1
0xf18  brfalse.s loc_F20
0xf1a  ldloc.1
0xf1b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf20  endfinally
0xf21  ldloc.0
0xf22  ret
```
