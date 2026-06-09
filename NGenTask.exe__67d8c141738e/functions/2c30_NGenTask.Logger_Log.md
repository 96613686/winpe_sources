# NGenTask.Logger::Log

- ea: `0x2c30`
- end: `0x2c53`
- name: `NGenTask.Logger::Log`
- size: `35`
- prototype: ``
- caller_count: `27`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x310`
- `0xec0`
- `0xf20`
- `0x1120`
- `0x11c0`
- `0x12d0`
- `0x1380`
- `0x1400`
- `0x1560`
- `0x19f0`
- `0x1ad0`
- `0x1e30`
- `0x24f0`
- `0x2540`
- `0x2610`
- `0x2790`
- `0x2910`
- `0x2990`
- `0x2c60`
- `0x2df0`
- `0x3790`
- `0x3830`
- `0x3c10`
- `0x4270`
- `0x45f0`
- `0x4fe0`
- `0x5310`

## callees

- `0x2c30`
- `0x2d00`

## pseudocode

```c

```

## disassembly

```asm
0x2c30  ldarg.0
0x2c31  ldsfld   valuetype LogLevel NGenTask.Logger::maxLogLevel
0x2c36  ble.s    loc_2C39
0x2c38  ret
0x2c39  ldarg.1
0x2c3a  ldarg.2
0x2c3b  call     string [mscorlib]System.String::Format(string, object[])
0x2c40  stloc.0
0x2c41  ldloc.0
0x2c42  call     void [mscorlib]System.Console::WriteLine(string)
0x2c47  leave.s  loc_2C4C
0x2c49  pop
0x2c4a  leave.s  loc_2C4C
0x2c4c  ldloc.0
0x2c4d  call     void NGenTask.Logger::CorSvcLog(string message)
0x2c52  ret
```
