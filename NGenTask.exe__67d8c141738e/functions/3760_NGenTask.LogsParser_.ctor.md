# NGenTask.LogsParser::.ctor

- ea: `0x3760`
- end: `0x3790`
- name: `NGenTask.LogsParser::.ctor`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x310`

## pseudocode

```c

```

## disassembly

```asm
0x3760  ldarg.0
0x3761  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x3766  stfld    class [System.Core]System.Collections.Generic.HashSet`1<string> NGenTask.LogsParser::m_SupportedBinders
0x376b  ldarg.0
0x376c  call     instance void [mscorlib]System.Object::.ctor()
0x3771  ldarg.0
0x3772  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> NGenTask.LogsParser::m_SupportedBinders
0x3777  ldarg.1
0x3778  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x377d  pop
0x377e  ldarg.0
0x377f  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> NGenTask.LogsParser::m_SupportedBinders
0x3784  ldstr    aWinrt// "WinRT"
0x3789  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x378e  pop
0x378f  ret
```
