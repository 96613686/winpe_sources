# ConsolePathMeter::Meter

- ea: `0x58e0`
- end: `0x5924`
- name: `ConsolePathMeter::Meter`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x58e0`

## pseudocode

```c

```

## disassembly

```asm
0x58e0  ldsfld   object ConsolePathMeter::ConsoleLockObj
0x58e5  stloc.0
0x58e6  ldc.i4.0
0x58e7  stloc.1
0x58e8  ldloc.0
0x58e9  ldloca.s 1
0x58eb  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x58f0  ldc.i4.s 0xA
0x58f2  call     void [mscorlib]System.Console::set_ForegroundColor(valuetype [mscorlib]System.ConsoleColor)
0x58f7  ldstr    a0T1// "==| {0:T} - {1}"
0x58fc  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::get_Now()
0x5901  box      [mscorlib]System.DateTimeOffset
0x5906  ldarg.2
0x5907  ldarg.3
0x5908  call     string [mscorlib]System.String::Format(string, object[])
0x590d  call     void [mscorlib]System.Console::WriteLine(string, object, object)
0x5912  call     void [mscorlib]System.Console::ResetColor()
0x5917  leave.s  loc_5923
0x5919  ldloc.1
0x591a  brfalse.s loc_5922
0x591c  ldloc.0
0x591d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5922  endfinally
0x5923  ret
```
