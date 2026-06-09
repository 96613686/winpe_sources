# System.Windows.Input.PenThreadPool::GetPenThreadForPenContextHelper

- ea: `0x4bec0`
- end: `0x4bf68`
- name: `System.Windows.Input.PenThreadPool::GetPenThreadForPenContextHelper`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x4be80`

## callees

- `0x4bd70`
- `0x4bdd0`
- `0x4bec0`
- `0x5bdd0`
- `0x5be40`

## string_xrefs

- `0x4bf47`: `GetPenThreadForPenContextHelper`

## pseudocode

```c

```

## disassembly

```asm
0x4bec0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.PenThread>::.ctor()
0x4bec5  stloc.3
0x4bec6  ldnull
0x4bec7  stloc.0
0x4bec8  br       loc_4BF51
0x4becd  ldarg.0
0x4bece  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>> System.Windows.Input.PenThreadPool::_penThreadWeakRefList
0x4bed3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>>::get_Count()
0x4bed8  ldc.i4.1
0x4bed9  sub
0x4beda  stloc.1
0x4bedb  br.s     loc_4BF14
0x4bedd  ldnull
0x4bede  stloc.2
0x4bedf  ldarg.0
0x4bee0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>> System.Windows.Input.PenThreadPool::_penThreadWeakRefList
0x4bee5  ldloc.1
0x4bee6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>>::get_Item(!!T0)
0x4beeb  ldloca.s 2
0x4beed  callvirt instance bool class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>::TryGetTarget(var<u1>&)
0x4bef2  brfalse.s loc_4BF01
0x4bef4  ldloc.3
0x4bef5  ldloc.2
0x4bef6  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.PenThread>::Contains(var<u1>)
0x4befb  brtrue.s loc_4BF01
0x4befd  ldloc.2
0x4befe  stloc.0
0x4beff  br.s     loc_4BF10
0x4bf01  ldloc.2
0x4bf02  brtrue.s loc_4BF10
0x4bf04  ldarg.0
0x4bf05  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>> System.Windows.Input.PenThreadPool::_penThreadWeakRefList
0x4bf0a  ldloc.1
0x4bf0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>>::RemoveAt(int32)
0x4bf10  ldloc.1
0x4bf11  ldc.i4.1
0x4bf12  sub
0x4bf13  stloc.1
0x4bf14  ldloc.1
0x4bf15  ldc.i4.0
0x4bf16  bge.s    loc_4BEDD
0x4bf18  ldloc.0
0x4bf19  brtrue.s loc_4BF32
0x4bf1b  newobj   instance void System.Windows.Input.PenThread::.ctor()
0x4bf20  stloc.0
0x4bf21  ldarg.0
0x4bf22  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>> System.Windows.Input.PenThreadPool::_penThreadWeakRefList
0x4bf27  ldloc.0
0x4bf28  newobj   instance void class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>::.ctor(var<u1>)
0x4bf2d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.WeakReference`1<class System.Windows.Input.PenThread>>::Add(var<u1>)
0x4bf32  ldarg.1
0x4bf33  brfalse.s loc_4BF5E
0x4bf35  ldloc.0
0x4bf36  ldarg.1
0x4bf37  callvirt instance bool System.Windows.Input.PenThread::AddPenContext(class System.Windows.Input.PenContext penContext)
0x4bf3c  brtrue.s loc_4BF5E
0x4bf3e  ldloc.3
0x4bf3f  ldloc.0
0x4bf40  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.PenThread>::Add(var<u1>)
0x4bf45  ldnull
0x4bf46  stloc.0
0x4bf47  ldstr    aGetpenthreadfo// "GetPenThreadForPenContextHelper"
0x4bf4c  call     void System.Windows.Input.Tracing.StylusTraceLogger::LogReentrancy([opt] string functionName)
0x4bf51  ldloc.3
0x4bf52  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Input.PenThread>::get_Count()
0x4bf57  ldc.i4.s 0xA
0x4bf59  blt      loc_4BECD
0x4bf5e  ldloc.0
0x4bf5f  brtrue.s loc_4BF66
0x4bf61  call     void System.Windows.Input.Tracing.StylusTraceLogger::LogReentrancyRetryLimitReached()
0x4bf66  ldloc.0
0x4bf67  ret
```
