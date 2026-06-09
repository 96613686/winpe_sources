# System.Windows.Input.PenThreadWorker::FireEvent

- ea: `0x4c540`
- end: `0x4c62a`
- name: `System.Windows.Input.PenThreadWorker::FireEvent`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x4caf0`

## callees

- `0x4b0d0`
- `0x4b110`
- `0x4b150`
- `0x4b1c0`
- `0x4b250`
- `0x4b320`
- `0x4b380`
- `0x4c420`
- `0x4c490`
- `0x4c540`
- `0x146e40`

## string_xrefs

- `0x4c551`: `PenService_InvalidPacketData`

## pseudocode

```c

```

## disassembly

```asm
0x4c540  ldarg.0
0x4c541  volatile.
0x4c543  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool System.Windows.Input.PenThreadWorker::__disposed
0x4c548  brfalse.s loc_4C54B
0x4c54a  ret
0x4c54b  ldarg.s  5
0x4c54d  ldc.i4.4
0x4c54e  rem
0x4c54f  brfalse.s loc_4C561
0x4c551  ldstr    aPenserviceInva// "PenService_InvalidPacketData"
0x4c556  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x4c55b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x4c560  throw
0x4c561  ldarg.s  4
0x4c563  ldarg.s  5
0x4c565  ldc.i4.4
0x4c566  div
0x4c567  mul
0x4c568  stloc.2
0x4c569  ldnull
0x4c56a  stloc.0
0x4c56b  ldc.i4.0
0x4c56c  ldloc.2
0x4c56d  bge.s    loc_4C58B
0x4c56f  ldloc.2
0x4c570  newarr   [mscorlib]System.Int32
0x4c575  stloc.0
0x4c576  ldarg.s  6
0x4c578  ldloc.0
0x4c579  ldc.i4.0
0x4c57a  ldloc.2
0x4c57b  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, int32[], int32, int32)
0x4c580  ldarg.1
0x4c581  ldloc.0
0x4c582  ldarg.s  4
0x4c584  callvirt instance void System.Windows.Input.PenContext::CheckForRectMappingChanged(int32[] data, int32 numPackets)
0x4c589  br.s     loc_4C58D
0x4c58b  ldnull
0x4c58c  stloc.0
0x4c58d  call     int32 [mscorlib]System.Environment::get_TickCount()
0x4c592  stloc.1
0x4c593  ldarg.0
0x4c594  ldarg.2
0x4c595  ldarg.1
0x4c596  ldarg.3
0x4c597  ldloc.0
0x4c598  ldloc.1
0x4c599  call     instance bool System.Windows.Input.PenThreadWorker::DoCacheEvent(int32 evt, class System.Windows.Input.PenContext penContext, int32 stylusPointerId, int32[] data, int32 timestamp)
0x4c59e  brfalse.s loc_4C5A1
0x4c5a0  ret
0x4c5a1  ldarg.0
0x4c5a2  ldc.i4.0
0x4c5a3  call     instance void System.Windows.Input.PenThreadWorker::FlushCache(bool goingOutOfRange)
0x4c5a8  ldarg.2
0x4c5a9  ldc.i4   0x2C3
0x4c5ae  sub
0x4c5af  switch   loc_4C60E, loc_4C618, loc_4C5D5, loc_4C5E8, loc_4C5FB, loc_4C629, loc_4C629, loc_4C621
0x4c5d4  ret
0x4c5d5  ldarg.1
0x4c5d6  ldarg.3
0x4c5d7  ldloc.0
0x4c5d8  ldloc.1
0x4c5d9  callvirt instance void System.Windows.Input.PenContext::FirePenInRange(int32 stylusPointerId, int32[] data, int32 timestamp)
0x4c5de  ldarg.1
0x4c5df  ldarg.3
0x4c5e0  ldloc.0
0x4c5e1  ldloc.1
0x4c5e2  callvirt instance void System.Windows.Input.PenContext::FirePenDown(int32 stylusPointerId, int32[] data, int32 timestamp)
0x4c5e7  ret
0x4c5e8  ldarg.1
0x4c5e9  ldarg.3
0x4c5ea  ldloc.0
0x4c5eb  ldloc.1
0x4c5ec  callvirt instance void System.Windows.Input.PenContext::FirePenInRange(int32 stylusPointerId, int32[] data, int32 timestamp)
0x4c5f1  ldarg.1
0x4c5f2  ldarg.3
0x4c5f3  ldloc.0
0x4c5f4  ldloc.1
0x4c5f5  callvirt instance void System.Windows.Input.PenContext::FirePenUp(int32 stylusPointerId, int32[] data, int32 timestamp)
0x4c5fa  ret
0x4c5fb  ldarg.1
0x4c5fc  ldarg.3
0x4c5fd  ldloc.0
0x4c5fe  ldloc.1
0x4c5ff  callvirt instance void System.Windows.Input.PenContext::FirePenInRange(int32 stylusPointerId, int32[] data, int32 timestamp)
0x4c604  ldarg.1
0x4c605  ldarg.3
0x4c606  ldloc.0
0x4c607  ldloc.1
0x4c608  callvirt instance void System.Windows.Input.PenContext::FirePackets(int32 stylusPointerId, int32[] data, int32 timestamp)
0x4c60d  ret
0x4c60e  ldarg.1
0x4c60f  ldarg.3
0x4c610  ldnull
0x4c611  ldloc.1
0x4c612  callvirt instance void System.Windows.Input.PenContext::FirePenInRange(int32 stylusPointerId, int32[] data, int32 timestamp)
0x4c617  ret
0x4c618  ldarg.1
0x4c619  ldarg.3
0x4c61a  ldloc.1
0x4c61b  callvirt instance void System.Windows.Input.PenContext::FirePenOutOfRange(int32 stylusPointerId, int32 timestamp)
0x4c620  ret
0x4c621  ldarg.1
0x4c622  ldarg.3
0x4c623  ldloc.1
0x4c624  callvirt instance void System.Windows.Input.PenContext::FireSystemGesture(int32 stylusPointerId, int32 timestamp)
0x4c629  ret
```
