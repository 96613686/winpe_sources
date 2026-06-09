# Microsoft.BIServer.HostingEnvironment.TimeMeter::.ctor_0

- ea: `0x22e0`
- end: `0x22f9`
- name: `Microsoft.BIServer.HostingEnvironment.TimeMeter::.ctor_0`
- size: `25`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1810`
- `0x22d0`
- `0x2540`
- `0x56f0`
- `0x5700`

## pseudocode

```c

```

## disassembly

```asm
0x22e0  ldarg.0
0x22e1  call     instance void [mscorlib]System.Object::.ctor()
0x22e6  ldarg.0
0x22e7  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x22ec  stfld    class [System]System.Diagnostics.Stopwatch Microsoft.BIServer.HostingEnvironment.TimeMeter::stopWatch
0x22f1  ldarg.0
0x22f2  ldarg.1
0x22f3  stfld    class MeterData Microsoft.BIServer.HostingEnvironment.TimeMeter::_reportTo
0x22f8  ret
```
