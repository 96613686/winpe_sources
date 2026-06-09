# Microsoft.BIServer.BIService.ConsoleDriver::EchoCmds

- ea: `0x15d0`
- end: `0x15e5`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::EchoCmds`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1520`

## string_xrefs

- `0x15d0`: `Format is "command arg"\nAvailable commands: (r)estart, (k)ill, (s)tart, (p)rocesses, (l)oad, (?)help`

## pseudocode

```c

```

## disassembly

```asm
0x15d0  ldstr    aFormatIsComman// "Format is \"command arg\"\nAvailable co"...
0x15d5  call     void [mscorlib]System.Console::WriteLine(string)
0x15da  ldstr    aHitCtrlCToExit// "Hit Ctrl-C to exit..."
0x15df  call     void [mscorlib]System.Console::WriteLine(string)
0x15e4  ret
```
