# Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::InitiateMemoryShrink

- ea: `0xee00`
- end: `0xf1ce`
- name: `Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::InitiateMemoryShrink`
- size: `974`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0xf480`

## callees

- `0xec20`
- `0xec30`
- `0xec40`
- `0xec60`
- `0xee00`
- `0xf1d0`
- `0xf200`
- `0xf2e0`
- `0xf420`

## string_xrefs

- `0xee53`: `{0} ms has elapsed since last memory shrink attempt for this appdomain ({1})`
- `0xee78`: `{0} ms has elapsed since last memory shrink attempt`
- `0xf181`: `Error while attempting to perform memory shrink: {0}`
- `0xf1a0`: `Error while attempting to perform memory shrink: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xee00  ldc.i4.0
0xee01  stloc.0
0xee02  ldarg.3
0xee03  ldc.i4.0
0xee04  conv.i8
0xee05  stind.i8
0xee06  ldarg.s  4
0xee08  ldc.i4.0
0xee09  conv.i8
0xee0a  stind.i8
0xee0b  ldsfld   class Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_current
0xee10  stloc.1
0xee11  ldloc.1
0xee12  ldfld    int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_timeFinishedLastNotification
0xee17  ldc.i4.0
0xee18  conv.i8
0xee19  ble.s    loc_EE8E
0xee1b  ldloc.1
0xee1c  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_intervalTimer
0xee21  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xee26  stloc.s  6
0xee28  ldloc.1
0xee29  ldarg.0
0xee2a  ldloc.s  6
0xee2c  callvirt instance bool Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::ShouldPerformShrink(int64 kBytes, int64 currentTime)
0xee31  brtrue.s loc_EE3B
0xee33  ldc.i4.0
0xee34  stloc.s  8
0xee36  leave    loc_F1CB
0xee3b  ldc.i4.0
0xee3c  conv.i8
0xee3d  ldloc.s  6
0xee3f  ldloc.1
0xee40  ldfld    int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_timeFinishedLastNotification
0xee45  sub
0xee46  call     int64 [mscorlib]System.Math::Max(int64, int64)
0xee4b  stloc.s  7
0xee4d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0xee52  ldc.i4.4
0xee53  ldstr    a0MsHasElapsedS// "{0} ms has elapsed since last memory sh"...
0xee58  ldloc.s  7
0xee5a  box      [mscorlib]System.Int64
0xee5f  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0xee64  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0xee69  call     string [mscorlib]System.String::Format(string, object, object)
0xee6e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xee73  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0xee78  ldstr    a0MsHasElapsedS_0// "{0} ms has elapsed since last memory sh"...
0xee7d  ldloc.s  7
0xee7f  box      [mscorlib]System.Int64
0xee84  call     string [mscorlib]System.String::Format(string, object)
0xee89  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0xee8e  ldc.i4.1
0xee8f  stloc.0
0xee90  newobj   instance void class Microsoft.ReportingServices.Diagnostics.PriorityQueue`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::.ctor()
0xee95  stloc.2
0xee96  ldc.i4.0
0xee97  conv.i8
0xee98  stloc.3
0xee99  ldloc.1
0xee9a  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_intervalTimer
0xee9f  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xeea4  stloc.s  4
0xeea6  ldloc.1
0xeea7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.WeakReference, class [mscorlib]System.WeakReference> Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_maps
0xeeac  stloc.s  9
0xeeae  ldc.i4.0
0xeeaf  stloc.s  0xA
0xeeb1  ldloc.s  9
0xeeb3  ldloca.s 0xA
0xeeb5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xeeba  ldloc.1
0xeebb  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy> Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::GetProxies(class Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection currentGroup)
0xeec0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::GetEnumerator()
0xeec5  stloc.s  0xB
0xeec7  br       loc_EF4C
0xeecc  ldloc.s  0xB
0xeece  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::get_Current()
0xeed3  stloc.s  0xC
0xeed5  ldc.i4.0
0xeed6  conv.i8
0xeed7  ldloc.s  0xC
0xeed9  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_CurrentMemoryUsageKBytes()
0xeede  call     int64 [mscorlib]System.Math::Max(int64, int64)
0xeee3  stloc.s  0xD
0xeee5  ldc.i4.0
0xeee6  conv.i8
0xeee7  ldloc.s  0xC
0xeee9  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_CurrentFreeableMemoryKBytes()
0xeeee  call     int64 [mscorlib]System.Math::Max(int64, int64)
0xeef3  stloc.s  0xE
0xeef5  ldc.i4.0
0xeef6  conv.i8
0xeef7  ldloc.s  0xC
0xeef9  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_PendingFreeKBytes()
0xeefe  call     int64 [mscorlib]System.Math::Max(int64, int64)
0xef03  stloc.s  0xF
0xef05  ldarg.s  4
0xef07  ldarg.s  4
0xef09  ldind.i8
0xef0a  ldloc.s  0xD
0xef0c  add
0xef0d  stind.i8
0xef0e  ldloc.3
0xef0f  ldloc.s  0xE
0xef11  add
0xef12  stloc.3
0xef13  ldloc.s  0xF
0xef15  ldc.i4.0
0xef16  conv.i8
0xef17  ble.s    loc_EF26
0xef19  ldarg.0
0xef1a  ldloc.s  0xF
0xef1c  sub
0xef1d  starg.s  0
0xef1f  ldarg.3
0xef20  ldarg.3
0xef21  ldind.i8
0xef22  ldloc.s  0xF
0xef24  add
0xef25  stind.i8
0xef26  ldloc.s  0xC
0xef28  call     int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::ComputeMapScore(class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy map)
0xef2d  stloc.s  0x10
0xef2f  ldloc.2
0xef30  ldloc.s  0xC
0xef32  ldloc.s  0x10
0xef34  callvirt instance int64 class Microsoft.ReportingServices.Diagnostics.PriorityQueue`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::Push(var<u1>, !!T0)
0xef39  pop
0xef3a  ldarg.1
0xef3b  brfalse.s loc_EF4C
0xef3d  ldloc.s  0xF
0xef3f  ldc.i4.0
0xef40  conv.i8
0xef41  bgt.s    loc_EF4C
0xef43  ldloc.s  0xC
0xef45  ldloc.s  0xD
0xef47  callvirt instance void Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::SetNewMemoryTarget(int64 memoryTargetKBytes)
0xef4c  ldloc.s  0xB
0xef4e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xef53  brtrue   loc_EECC
0xef58  leave.s  loc_EF66
0xef5a  ldloc.s  0xB
0xef5c  brfalse.s loc_EF65
0xef5e  ldloc.s  0xB
0xef60  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xef65  endfinally
0xef66  leave.s  loc_EF74
0xef68  ldloc.s  0xA
0xef6a  brfalse.s loc_EF73
0xef6c  ldloc.s  9
0xef6e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xef73  endfinally
0xef74  ldloc.1
0xef75  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_intervalTimer
0xef7a  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xef7f  stloc.s  5
0xef81  ldarg.0
0xef82  ldc.i4.0
0xef83  conv.i8
0xef84  bge.s    loc_EFB6
0xef86  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0xef8b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0xef90  brfalse.s loc_EFA2
0xef92  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0xef97  ldc.i4.4
0xef98  ldstr    aMemoryShrinkRe// "Memory shrink request satisfied by pend"...
0xef9d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xefa2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0xefa7  ldstr    aMemoryShrinkRe// "Memory shrink request satisfied by pend"...
0xefac  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0xefb1  br       loc_F162
0xefb6  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0xefbb  callvirt instance int64 [System]System.Diagnostics.Process::get_PrivateMemorySize64()
0xefc0  ldc.i4   0x400
0xefc5  conv.i8
0xefc6  div
0xefc7  stloc.s  0x11
0xefc9  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0xefce  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0xefd3  brfalse.s loc_F017
0xefd5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0xefda  ldc.i4.4
0xefdb  ldstr    aMemoryStatisti// "Memory Statistics: {0} items, {1}KB Aud"...
0xefe0  ldc.i4.4
0xefe1  newarr   [mscorlib]System.Object
0xefe6  dup
0xefe7  ldc.i4.0
0xefe8  ldloc.2
0xefe9  callvirt instance int32 class Microsoft.ReportingServices.Diagnostics.PriorityQueue`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::get_Count()
0xefee  box      [mscorlib]System.Int32
0xeff3  stelem.ref
0xeff4  dup
0xeff5  ldc.i4.1
0xeff6  ldarg.s  4
0xeff8  ldind.i8
0xeff9  box      [mscorlib]System.Int64
0xeffe  stelem.ref
0xefff  dup
0xf000  ldc.i4.2
0xf001  ldloc.3
0xf002  box      [mscorlib]System.Int64
0xf007  stelem.ref
0xf008  dup
0xf009  ldc.i4.3
0xf00a  ldloc.s  0x11
0xf00c  box      [mscorlib]System.Int64
0xf011  stelem.ref
0xf012  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xf017  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_RdlEngineHostTracer()
0xf01c  ldstr    aMemoryStatisti// "Memory Statistics: {0} items, {1}KB Aud"...
0xf021  ldc.i4.4
0xf022  newarr   [mscorlib]System.Object
0xf027  dup
0xf028  ldc.i4.0
0xf029  ldloc.2
0xf02a  callvirt instance int32 class Microsoft.ReportingServices.Diagnostics.PriorityQueue`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::get_Count()
0xf02f  box      [mscorlib]System.Int32
0xf034  stelem.ref
0xf035  dup
0xf036  ldc.i4.1
0xf037  ldarg.s  4
0xf039  ldind.i8
0xf03a  box      [mscorlib]System.Int64
0xf03f  stelem.ref
0xf040  dup
0xf041  ldc.i4.2
0xf042  ldloc.3
0xf043  box      [mscorlib]System.Int64
0xf048  stelem.ref
0xf049  dup
0xf04a  ldc.i4.3
0xf04b  ldloc.s  0x11
0xf04d  box      [mscorlib]System.Int64
0xf052  stelem.ref
0xf053  call     string [mscorlib]System.String::Format(string, object[])
0xf058  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string)
0xf05d  ldloc.1
0xf05e  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_intervalTimer
0xf063  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xf068  stloc.s  0x12
0xf06a  ldloc.2
0xf06b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>> class Microsoft.ReportingServices.Diagnostics.PriorityQueue`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::GetPoppingIterator()
0xf070  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::GetEnumerator()
0xf075  stloc.s  0xB
0xf077  br.s     loc_F0BE
0xf079  ldloc.s  0xB
0xf07b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy>::get_Current()
0xf080  stloc.s  0x14
0xf082  ldloc.s  0x14
0xf084  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_CurrentMemoryUsageKBytes()
0xf089  stloc.s  0x15
0xf08b  ldarg.0
0xf08c  ldloc.s  0x14
0xf08e  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::get_CurrentFreeableMemoryKBytes()
0xf093  call     int64 [mscorlib]System.Math::Min(int64, int64)
0xf098  stloc.s  0x16
0xf09a  ldloc.s  0x16
0xf09c  ldc.i4.s 0x40
0xf09e  conv.i8
0xf09f  blt.s    loc_F0C7
0xf0a1  ldloc.s  0x15
0xf0a3  ldloc.s  0x16
0xf0a5  sub
0xf0a6  stloc.s  0x17
0xf0a8  ldloc.s  0x14
0xf0aa  ldloc.s  0x17
0xf0ac  callvirt instance void Microsoft.ReportingServices.Diagnostics.MemoryAuditProxy::SetNewMemoryTarget(int64 memoryTargetKBytes)
0xf0b1  ldarg.0
0xf0b2  ldloc.s  0x16
0xf0b4  sub
0xf0b5  starg.s  0
0xf0b7  ldarg.3
0xf0b8  ldarg.3
0xf0b9  ldind.i8
0xf0ba  ldloc.s  0x16
0xf0bc  add
0xf0bd  stind.i8
0xf0be  ldloc.s  0xB
0xf0c0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf0c5  brtrue.s loc_F079
0xf0c7  leave.s  loc_F0D5
0xf0c9  ldloc.s  0xB
0xf0cb  brfalse.s loc_F0D4
0xf0cd  ldloc.s  0xB
0xf0cf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf0d4  endfinally
0xf0d5  ldloc.1
0xf0d6  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::m_intervalTimer
0xf0db  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xf0e0  stloc.s  0x13
0xf0e2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0xf0e7  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0xf0ec  brfalse.s loc_F12C
0xf0ee  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_AppDomainManagerTracer()
0xf0f3  ldc.i4.4
0xf0f4  ldstr    aSpent0MsEnumer// "Spent {0}ms enumerating MAP items and {"...
0xf0f9  ldc.i4.2
0xf0fa  newarr   [mscorlib]System.Object
0xf0ff  dup
  ... truncated ...
```
