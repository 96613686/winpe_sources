# Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use

- ea: `0x1bb0`
- end: `0x1bd1`
- name: `Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1be0`
- `0x2cf0`

## callees

- `0xc80`
- `0x1bb0`
- `0x1c00`
- `0x5930`
- `0x5970`

## pseudocode

```c

```

## disassembly

```asm
0x1bb0  call     bool Microsoft.BIServer.HostingEnvironment.Logger::get_MetricsEnabled()
0x1bb5  brtrue.s loc_1BBD
0x1bb7  newobj   instance void NoOpPathMeter::.ctor()
0x1bbc  ret
0x1bbd  call     bool [mscorlib]System.Environment::get_UserInteractive()
0x1bc2  brfalse.s loc_1BCA
0x1bc4  newobj   instance void ConsolePathMeter::.ctor()
0x1bc9  ret
0x1bca  ldarg.0
0x1bcb  newobj   instance void Microsoft.BIServer.HostingEnvironment.ScopeMeter::.ctor(string name)
0x1bd0  ret
```
