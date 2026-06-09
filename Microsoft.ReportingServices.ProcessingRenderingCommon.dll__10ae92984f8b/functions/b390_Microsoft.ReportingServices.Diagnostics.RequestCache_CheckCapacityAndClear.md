# Microsoft.ReportingServices.Diagnostics.RequestCache::CheckCapacityAndClear

- ea: `0xb390`
- end: `0xb436`
- name: `Microsoft.ReportingServices.Diagnostics.RequestCache::CheckCapacityAndClear`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xb340`

## callees

- `0xb390`
- `0x15c40`
- `0x15c60`
- `0x15cc0`

## pseudocode

```c

```

## disassembly

```asm
0xb390  ldarg.1
0xb391  ldc.i4.1
0xb392  beq.s    loc_B3A4
0xb394  ldstr    aN// "n"
0xb399  ldstr    aOnlySupportedW// "only supported when n == 1"
0xb39e  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, string)
0xb3a3  throw
0xb3a4  ldc.i4.0
0xb3a5  stloc.0
0xb3a6  ldarg.0
0xb3a7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class CacheObject> Microsoft.ReportingServices.Diagnostics.RequestCache::m_cache
0xb3ac  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class CacheObject>::get_Count()
0xb3b1  ldarg.1
0xb3b2  add
0xb3b3  ldarg.0
0xb3b4  ldfld    int32 Microsoft.ReportingServices.Diagnostics.RequestCache::m_totalSlots
0xb3b9  sub
0xb3ba  stloc.0
0xb3bb  br.s     loc_B42A
0xb3bd  ldnull
0xb3be  stloc.1
0xb3bf  ldarg.0
0xb3c0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class CacheObject> Microsoft.ReportingServices.Diagnostics.RequestCache::m_cache
0xb3c5  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class CacheObject>::get_Values()
0xb3ca  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class CacheObject>::GetEnumerator()
0xb3cf  stloc.2
0xb3d0  br.s     loc_B3F2
0xb3d2  ldloca.s 2
0xb3d4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class CacheObject>::get_Current()
0xb3d9  stloc.3
0xb3da  ldloc.1
0xb3db  brfalse.s loc_B3F0
0xb3dd  ldloc.3
0xb3de  callvirt instance valuetype [mscorlib]System.DateTime CacheObject::get_LastTimeAccessed()
0xb3e3  ldloc.1
0xb3e4  callvirt instance valuetype [mscorlib]System.DateTime CacheObject::get_LastTimeAccessed()
0xb3e9  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xb3ee  brfalse.s loc_B3F2
0xb3f0  ldloc.3
0xb3f1  stloc.1
0xb3f2  ldloca.s 2
0xb3f4  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class CacheObject>::MoveNext()
0xb3f9  brtrue.s loc_B3D2
0xb3fb  leave.s  loc_B40B
0xb3fd  ldloca.s 2
0xb3ff  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class CacheObject>
0xb405  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb40a  endfinally
0xb40b  ldloc.1
0xb40c  brfalse.s loc_B42E
0xb40e  ldloc.1
0xb40f  callvirt instance void CacheObject::Dispose()
0xb414  ldarg.0
0xb415  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class CacheObject> Microsoft.ReportingServices.Diagnostics.RequestCache::m_cache
0xb41a  ldloc.1
0xb41b  callvirt instance string CacheObject::get_Key()
0xb420  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class CacheObject>::Remove(var<u1>)
0xb425  pop
0xb426  ldloc.0
0xb427  ldc.i4.1
0xb428  sub
0xb429  stloc.0
0xb42a  ldloc.0
0xb42b  ldc.i4.0
0xb42c  bgt.s    loc_B3BD
0xb42e  ldloc.0
0xb42f  ldc.i4.0
0xb430  cgt
0xb432  ldc.i4.0
0xb433  ceq
0xb435  ret
```
