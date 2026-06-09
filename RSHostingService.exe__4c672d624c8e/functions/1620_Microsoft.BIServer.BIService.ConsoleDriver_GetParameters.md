# Microsoft.BIServer.BIService.ConsoleDriver::GetParameters

- ea: `0x1620`
- end: `0x1663`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::GetParameters`
- size: `67`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x16a0`
- `0x16e0`
- `0x1740`
- `0x17a0`

## callees

- `0x1620`

## pseudocode

```c

```

## disassembly

```asm
0x1620  ldstr    aEnterSpaceDeli// "Enter space-delimited list of {0} to {1"...
0x1625  ldarg.0
0x1626  ldarg.1
0x1627  call     void [mscorlib]System.Console::WriteLine(string, object, object)
0x162c  call     string [mscorlib]System.Console::ReadLine()
0x1631  ldc.i4.1
0x1632  newarr   [mscorlib]System.Char
0x1637  dup
0x1638  ldc.i4.0
0x1639  ldc.i4.s 0x20
0x163b  stelem.i2
0x163c  callvirt instance string [mscorlib]System.String::Trim(char[])
0x1641  stloc.0
0x1642  ldloc.0
0x1643  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1648  brfalse.s loc_1651
0x164a  ldc.i4.0
0x164b  newarr   [mscorlib]System.String
0x1650  ret
0x1651  ldloc.0
0x1652  ldc.i4.1
0x1653  newarr   [mscorlib]System.Char
0x1658  dup
0x1659  ldc.i4.0
0x165a  ldc.i4.s 0x20
0x165c  stelem.i2
0x165d  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1662  ret
```
