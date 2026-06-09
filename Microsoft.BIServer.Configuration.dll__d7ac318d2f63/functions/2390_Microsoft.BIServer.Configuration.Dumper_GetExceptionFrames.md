# Microsoft.BIServer.Configuration.Dumper::GetExceptionFrames

- ea: `0x2390`
- end: `0x245e`
- name: `Microsoft.BIServer.Configuration.Dumper::GetExceptionFrames`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2230`

## callees

- `0x2390`

## pseudocode

```c

```

## disassembly

```asm
0x2390  ldarg.1
0x2391  ldc.i4.0
0x2392  stind.i4
0x2393  ldarg.0
0x2394  brtrue.s loc_2398
0x2396  ldnull
0x2397  ret
0x2398  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Diagnostics.StackTrace>::.ctor()
0x239d  stloc.0
0x239e  ldc.i4.0
0x239f  stloc.1
0x23a0  br.s     loc_23D5
0x23a2  ldarg.0
0x23a3  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor(class [mscorlib]System.Exception)
0x23a8  stloc.s  4
0x23aa  ldloc.s  4
0x23ac  callvirt instance int32 [mscorlib]System.Diagnostics.StackTrace::get_FrameCount()
0x23b1  brtrue.s loc_23BB
0x23b3  ldc.i4.0
0x23b4  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor(bool)
0x23b9  stloc.s  4
0x23bb  ldloc.1
0x23bc  ldloc.s  4
0x23be  callvirt instance int32 [mscorlib]System.Diagnostics.StackTrace::get_FrameCount()
0x23c3  add
0x23c4  stloc.1
0x23c5  ldloc.0
0x23c6  ldloc.s  4
0x23c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Diagnostics.StackTrace>::Add(var<u1>)
0x23cd  ldarg.0
0x23ce  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x23d3  starg.s  0
0x23d5  ldarg.0
0x23d6  brtrue.s loc_23A2
0x23d8  ldc.i4.0
0x23d9  stloc.2
0x23da  ldc.i4.4
0x23db  ldloc.1
0x23dc  mul
0x23dd  newarr   [mscorlib]System.Byte
0x23e2  stloc.3
0x23e3  ldloc.0
0x23e4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Diagnostics.StackTrace>::GetEnumerator()
0x23e9  stloc.s  5
0x23eb  br.s     loc_2436
0x23ed  ldloca.s 5
0x23ef  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Diagnostics.StackTrace>::get_Current()
0x23f4  stloc.s  6
0x23f6  ldloc.s  6
0x23f8  callvirt instance int32 [mscorlib]System.Diagnostics.StackTrace::get_FrameCount()
0x23fd  ldc.i4.0
0x23fe  ble.s    loc_2436
0x2400  ldloc.s  6
0x2402  callvirt instance class [mscorlib]System.Diagnostics.StackFrame[] [mscorlib]System.Diagnostics.StackTrace::GetFrames()
0x2407  stloc.s  7
0x2409  ldc.i4.0
0x240a  stloc.s  8
0x240c  br.s     loc_242E
0x240e  ldloc.s  7
0x2410  ldloc.s  8
0x2412  ldelem.ref
0x2413  callvirt instance int32 [mscorlib]System.Diagnostics.StackFrame::GetNativeOffset()
0x2418  call     unsigned int8[] [mscorlib]System.BitConverter::GetBytes(int32)
0x241d  ldloc.3
0x241e  ldloc.2
0x241f  callvirt instance void [mscorlib]System.Array::CopyTo(class [mscorlib]System.Array, int32)
0x2424  ldloc.2
0x2425  ldc.i4.4
0x2426  add
0x2427  stloc.2
0x2428  ldloc.s  8
0x242a  ldc.i4.1
0x242b  add
0x242c  stloc.s  8
0x242e  ldloc.s  8
0x2430  ldloc.s  7
0x2432  ldlen
0x2433  conv.i4
0x2434  blt.s    loc_240E
0x2436  ldloca.s 5
0x2438  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Diagnostics.StackTrace>::MoveNext()
0x243d  brtrue.s loc_23ED
0x243f  leave.s  loc_244F
0x2441  ldloca.s 5
0x2443  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Diagnostics.StackTrace>
0x2449  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x244e  endfinally
0x244f  ldarg.1
0x2450  ldloc.3
0x2451  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x2456  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x245b  stind.i4
0x245c  ldloc.3
0x245d  ret
```
