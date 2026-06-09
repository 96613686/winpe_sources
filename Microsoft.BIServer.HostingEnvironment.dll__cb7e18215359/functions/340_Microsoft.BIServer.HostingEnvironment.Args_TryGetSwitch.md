# Microsoft.BIServer.HostingEnvironment.Args::TryGetSwitch

- ea: `0x340`
- end: `0x34e`
- name: `Microsoft.BIServer.HostingEnvironment.Args::TryGetSwitch`
- size: `14`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7a0`
- `0x7c0`
- `0x820`
- `0x870`
- `0xdb0`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldarg.0
0x341  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.HostingEnvironment.Args::_switches
0x346  ldarg.1
0x347  ldarg.2
0x348  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x34d  ret
```
