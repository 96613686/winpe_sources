# Microsoft.BIServer.HostingEnvironment.Args::.ctor

- ea: `0x1c0`
- end: `0x1e4`
- name: `Microsoft.BIServer.HostingEnvironment.Args::.ctor`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x220`
- `0x750`

## callees

- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.0
0x1c1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1c6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.HostingEnvironment.Args::_switches
0x1cb  ldarg.0
0x1cc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1d1  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.BIServer.HostingEnvironment.Args::_nonSwitches
0x1d6  ldarg.0
0x1d7  call     instance void [mscorlib]System.Object::.ctor()
0x1dc  ldarg.0
0x1dd  ldarg.1
0x1de  call     instance void Microsoft.BIServer.HostingEnvironment.Args::SetArgs(string[] args)
0x1e3  ret
```
