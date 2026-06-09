# Microsoft.BIServer.HostingEnvironment.BIProcess::<Update>b__8_0

- ea: `0x6f0`
- end: `0x702`
- name: `Microsoft.BIServer.HostingEnvironment.BIProcess::<Update>b__8_0`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldarg.1
0x6f1  callvirt instance string [System]System.Diagnostics.Process::get_ProcessName()
0x6f6  ldarg.0
0x6f7  ldfld    string Microsoft.BIServer.HostingEnvironment.BIProcess::_processName
0x6fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x701  ret
```
