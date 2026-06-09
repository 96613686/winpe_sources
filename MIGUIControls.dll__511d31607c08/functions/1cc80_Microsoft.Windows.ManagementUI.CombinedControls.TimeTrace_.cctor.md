# Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::.cctor

- ea: `0x1cc80`
- end: `0x1ccb3`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::.cctor`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x1cc85`: `Switch in config file`
- `0x1cc99`: `Switch in config file`
- `0x1cc94`: `TaskSchedulerTrace`

## pseudocode

```c

```

## disassembly

```asm
0x1cc80  ldstr    aEventviewertra// "EventViewerTrace"
0x1cc85  ldstr    aSwitchInConfig// "Switch in config file"
0x1cc8a  newobj   instance void [System]System.Diagnostics.BooleanSwitch::.ctor(string, string)
0x1cc8f  stsfld   class [System]System.Diagnostics.BooleanSwitch Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::evSwitch
0x1cc94  ldstr    aTaskschedulert// "TaskSchedulerTrace"
0x1cc99  ldstr    aSwitchInConfig// "Switch in config file"
0x1cc9e  newobj   instance void [System]System.Diagnostics.BooleanSwitch::.ctor(string, string)
0x1cca3  stsfld   class [System]System.Diagnostics.BooleanSwitch Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::tsSwitch
0x1cca8  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::.ctor()
0x1ccad  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::_methodStartTimes
0x1ccb2  ret
```
