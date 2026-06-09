# Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::Initialize

- ea: `0x6810`
- end: `0x6871`
- name: `Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::Initialize`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x44c0`

## callees

- `0x6810`
- `0x68f0`
- `0x6900`

## pseudocode

```c

```

## disassembly

```asm
0x6810  ldarg.0
0x6811  call     instance object Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::get_SyncRoot()
0x6816  dup
0x6817  stloc.1
0x6818  call     void [mscorlib]System.Threading.Monitor::Enter(object)
0x681d  ldarg.0
0x681e  ldarg.1
0x681f  stfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_snapInPlatform
0x6824  ldarg.0
0x6825  ldfld    class [mscorlib]System.Collections.Generic.List`1<unsigned int64> Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_registeredThreadIds
0x682a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::GetEnumerator()
0x682f  stloc.2
0x6830  br.s     loc_6843
0x6832  ldloca.s 2
0x6834  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<unsigned int64>::get_Current()
0x6839  conv.u4
0x683a  stloc.0
0x683b  ldarg.0
0x683c  ldloc.0
0x683d  ldc.i4.1
0x683e  call     instance void Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::RegisterThreadWithExecutive(unsigned int32 threadId, bool register)
0x6843  ldloca.s 2
0x6845  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<unsigned int64>::MoveNext()
0x684a  brtrue.s loc_6832
0x684c  leave.s  loc_685C
0x684e  ldloca.s 2
0x6850  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<unsigned int64>
0x6856  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x685b  endfinally
0x685c  ldarg.0
0x685d  ldfld    class [mscorlib]System.Collections.Generic.List`1<unsigned int64> Microsoft.ManagementConsole.Internal.SnapInUIThreadTable::_registeredThreadIds
0x6862  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::Clear()
0x6867  leave.s  loc_6870
0x6869  ldloc.1
0x686a  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x686f  endfinally
0x6870  ret
```
