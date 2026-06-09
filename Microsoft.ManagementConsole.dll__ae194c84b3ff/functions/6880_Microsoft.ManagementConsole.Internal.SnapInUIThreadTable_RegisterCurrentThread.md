# Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::RegisterCurrentThread

- ea: `0x6880`
- end: `0x68ed`
- name: `Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::RegisterCurrentThread`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4740`
- `0x4750`

## callees

- `0x6880`
- `0x68f0`
- `0x6900`
- `0x85d0`

## pseudocode

```c

```

## disassembly

```asm
0x6880  call     int32 Microsoft.ManagementConsole.Interop.NativeMethods::GetCurrentThreadId()
0x6885  stloc.0
0x6886  ldarg.0
0x6887  call     instance object Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::get_SyncRoot()
0x688c  dup
0x688d  stloc.1
0x688e  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x6893  ldarg.0
0x6894  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_snapInPlatform
0x6899  brfalse.s loc_68A5
0x689b  ldarg.0
0x689c  ldloc.0
0x689d  ldarg.1
0x689e  call     instance void Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::RegisterThreadWithExecutive(unsigned int32 threadId, bool register)
0x68a3  br.s     loc_68E3
0x68a5  ldarg.1
0x68a6  brfalse.s loc_68C6
0x68a8  ldarg.0
0x68a9  ldfld    class [mscorlib]System.Collections.Generic.List`1<unsigned int64> Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_registeredThreadIds
0x68ae  ldloc.0
0x68af  conv.u8
0x68b0  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::Contains(var<u1>)
0x68b5  brtrue.s loc_68E3
0x68b7  ldarg.0
0x68b8  ldfld    class [mscorlib]System.Collections.Generic.List`1<unsigned int64> Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_registeredThreadIds
0x68bd  ldloc.0
0x68be  conv.u8
0x68bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::Add(var<u1>)
0x68c4  br.s     loc_68E3
0x68c6  ldarg.0
0x68c7  ldfld    class [mscorlib]System.Collections.Generic.List`1<unsigned int64> Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_registeredThreadIds
0x68cc  ldloc.0
0x68cd  conv.u8
0x68ce  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::Contains(var<u1>)
0x68d3  brfalse.s loc_68E3
0x68d5  ldarg.0
0x68d6  ldfld    class [mscorlib]System.Collections.Generic.List`1<unsigned int64> Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_registeredThreadIds
0x68db  ldloc.0
0x68dc  conv.u8
0x68dd  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::Remove(var<u1>)
0x68e2  pop
0x68e3  leave.s  loc_68EC
0x68e5  ldloc.1
0x68e6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x68eb  endfinally
0x68ec  ret
```
