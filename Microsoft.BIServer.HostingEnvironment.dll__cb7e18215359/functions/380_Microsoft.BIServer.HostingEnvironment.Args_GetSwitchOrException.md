# Microsoft.BIServer.HostingEnvironment.Args::GetSwitchOrException

- ea: `0x380`
- end: `0x3a3`
- name: `Microsoft.BIServer.HostingEnvironment.Args::GetSwitchOrException`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x380`

## string_xrefs

- `0x392`: `Missing required command line parameter [{0}]`

## pseudocode

```c

```

## disassembly

```asm
0x380  ldarg.0
0x381  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.HostingEnvironment.Args::_switches
0x386  ldarg.1
0x387  ldloca.s 0
0x389  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x38e  brfalse.s loc_392
0x390  ldloc.0
0x391  ret
0x392  ldstr    aMissingRequire// "Missing required command line parameter"...
0x397  ldarg.1
0x398  call     string [mscorlib]System.String::Format(string, object)
0x39d  newobj   instance void [mscorlib]System.Collections.Generic.KeyNotFoundException::.ctor(string)
0x3a2  throw
```
