# Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use_0

- ea: `0x1be0`
- end: `0x1bfe`
- name: `Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use_0`
- size: `30`
- prototype: ``
- caller_count: `11`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2870`
- `0x2960`
- `0x2a20`
- `0x2c30`
- `0x5bd0`
- `0x5de0`
- `0x5f20`
- `0x6070`
- `0x61c0`
- `0x63d0`
- `0x6510`

## callees

- `0xc80`
- `0x1bb0`
- `0x1be0`
- `0x5970`

## pseudocode

```c

```

## disassembly

```asm
0x1be0  call     bool Microsoft.BIServer.HostingEnvironment.Logger::get_MetricsEnabled()
0x1be5  brtrue.s loc_1BED
0x1be7  newobj   instance void NoOpPathMeter::.ctor()
0x1bec  ret
0x1bed  ldstr    asc_827C// "."
0x1bf2  ldarg.0
0x1bf3  call     string [mscorlib]System.String::Join(string, string[])
0x1bf8  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string name)
0x1bfd  ret
```
