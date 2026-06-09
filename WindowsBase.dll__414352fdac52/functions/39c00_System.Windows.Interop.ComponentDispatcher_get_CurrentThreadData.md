# System.Windows.Interop.ComponentDispatcher::get_CurrentThreadData

- ea: `0x39c00`
- end: `0x39c2a`
- name: `System.Windows.Interop.ComponentDispatcher::get_CurrentThreadData`
- size: `42`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x39c30`
- `0x39c50`
- `0x39c60`
- `0x39c70`
- `0x39c90`
- `0x39cb0`
- `0x39cc0`
- `0x39cd0`
- `0x39ce0`
- `0x39d00`
- `0x39d20`
- `0x39d40`
- `0x39d60`
- `0x39d70`
- `0x39d80`
- `0x39d90`
- `0x39da0`
- `0x39dc0`
- `0x39de0`
- `0x39e00`

## callees

- `0x39c00`
- `0x3a240`

## pseudocode

```c

```

## disassembly

```asm
0x39c00  ldsfld   class [mscorlib]System.LocalDataStoreSlot System.Windows.Interop.ComponentDispatcher::_threadSlot
0x39c05  call     object [mscorlib]System.Threading.Thread::GetData(class [mscorlib]System.LocalDataStoreSlot)
0x39c0a  stloc.1
0x39c0b  ldloc.1
0x39c0c  brtrue.s loc_39C21
0x39c0e  newobj   instance void System.Windows.Interop.ComponentDispatcherThread::.ctor()
0x39c13  stloc.0
0x39c14  ldsfld   class [mscorlib]System.LocalDataStoreSlot System.Windows.Interop.ComponentDispatcher::_threadSlot
0x39c19  ldloc.0
0x39c1a  call     void [mscorlib]System.Threading.Thread::SetData(class [mscorlib]System.LocalDataStoreSlot, object)
0x39c1f  br.s     loc_39C28
0x39c21  ldloc.1
0x39c22  castclass System.Windows.Interop.ComponentDispatcherThread
0x39c27  stloc.0
0x39c28  ldloc.0
0x39c29  ret
```
