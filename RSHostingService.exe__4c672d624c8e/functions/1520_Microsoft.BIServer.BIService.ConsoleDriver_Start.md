# Microsoft.BIServer.BIService.ConsoleDriver::Start

- ea: `0x1520`
- end: `0x15c7`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::Start`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x23e0`

## callees

- `0x1520`
- `0x15d0`
- `0x15f0`
- `0x1680`
- `0x16a0`
- `0x16e0`
- `0x1740`
- `0x17a0`

## string_xrefs

- `0x15b1`: `{0} is not a recognized command`

## pseudocode

```c

```

## disassembly

```asm
0x1520  ldarg.0
0x1521  ldftn    instance void Microsoft.BIServer.BIService.ConsoleDriver::ConsoleCancelQuitHandler(object sender, class [mscorlib]System.ConsoleCancelEventArgs args)
0x1527  newobj   instance void [mscorlib]System.ConsoleCancelEventHandler::.ctor(object, native int)
0x152c  call     void [mscorlib]System.Console::add_CancelKeyPress(class [mscorlib]System.ConsoleCancelEventHandler)
0x1531  ldarg.0
0x1532  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::EchoCmds()
0x1537  call     string Microsoft.BIServer.BIService.ConsoleDriver::GetCommand()
0x153c  stloc.0
0x153d  ldloc.0
0x153e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1543  brfalse.s loc_1537
0x1545  ldloc.0
0x1546  ldc.i4.0
0x1547  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x154c  stloc.1
0x154d  ldloc.1
0x154e  ldc.i4.s 0x3F
0x1550  beq.s    loc_15A9
0x1552  ldloc.1
0x1553  ldc.i4.s 0x6B
0x1555  sub
0x1556  switch   loc_1589, loc_15A1, loc_15B1, loc_15B1, loc_15B1, loc_1599, loc_15B1, loc_1581, loc_1591
0x157f  br.s     loc_15B1
0x1581  ldarg.0
0x1582  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::RestartCmd()
0x1587  br.s     loc_1537
0x1589  ldarg.0
0x158a  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::KillCmd()
0x158f  br.s     loc_1537
0x1591  ldarg.0
0x1592  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::StartCmd()
0x1597  br.s     loc_1537
0x1599  ldarg.0
0x159a  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::ListCmd()
0x159f  br.s     loc_1537
0x15a1  ldarg.0
0x15a2  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::LoadCmd()
0x15a7  br.s     loc_1537
0x15a9  ldarg.0
0x15aa  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::EchoCmds()
0x15af  br.s     loc_1537
0x15b1  ldstr    a0IsNotARecogni// "{0} is not a recognized command"
0x15b6  ldloc.0
0x15b7  call     void [mscorlib]System.Console::WriteLine(string, object)
0x15bc  ldarg.0
0x15bd  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::EchoCmds()
0x15c2  br       loc_1537
```
