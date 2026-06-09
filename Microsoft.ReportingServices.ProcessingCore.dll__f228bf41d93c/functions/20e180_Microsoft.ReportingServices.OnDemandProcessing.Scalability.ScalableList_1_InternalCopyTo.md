# Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1::InternalCopyTo

- ea: `0x20e180`
- end: `0x20e2ee`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1::InternalCopyTo`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x20b4f0`
- `0x20e180`

## string_xrefs

- `0x20e189`: `ScalableList.CopyTo: Dest array cannot be null`
- `0x20e19d`: `ScalableList.CopyTo: Index must not be less than 0`
- `0x20e1b1`: `ScalableList.CopyTo: Array must be one-dimensional`
- `0x20e1cc`: `ScalableList.CopyTo: Start index must be less than the size of the array`
- `0x20e1ec`: `ScalableList.CopyTo: Insufficent space in the target array`

## pseudocode

```c

```

## disassembly

```asm
0x20e180  ldarg.1
0x20e181  brtrue.s loc_20E193
0x20e183  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20e188  ldc.i4.0
0x20e189  ldstr    aScalablelistCo// "ScalableList.CopyTo: Dest array cannot "...
0x20e18e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20e193  ldarg.2
0x20e194  ldc.i4.0
0x20e195  bge.s    loc_20E1A7
0x20e197  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20e19c  ldc.i4.0
0x20e19d  ldstr    aScalablelistCo_0// "ScalableList.CopyTo: Index must not be "...
0x20e1a2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20e1a7  ldarg.2
0x20e1a8  ldc.i4.1
0x20e1a9  beq.s    loc_20E1BB
0x20e1ab  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20e1b0  ldc.i4.0
0x20e1b1  ldstr    aScalablelistCo_1// "ScalableList.CopyTo: Array must be one-"...
0x20e1b6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20e1bb  ldarg.2
0x20e1bc  ldarg.1
0x20e1bd  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x20e1c2  ldc.i4.1
0x20e1c3  sub
0x20e1c4  ble.s    loc_20E1D6
0x20e1c6  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20e1cb  ldc.i4.0
0x20e1cc  ldstr    aScalablelistCo_2// "ScalableList.CopyTo: Start index must b"...
0x20e1d1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20e1d6  ldarg.2
0x20e1d7  ldarg.0
0x20e1d8  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20e1dd  add
0x20e1de  ldarg.1
0x20e1df  callvirt instance int32 [mscorlib]System.Array::get_Length()
0x20e1e4  ble.s    loc_20E1F6
0x20e1e6  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20e1eb  ldc.i4.0
0x20e1ec  ldstr    aScalablelistCo_3// "ScalableList.CopyTo: Insufficent space "...
0x20e1f1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20e1f6  ldarg.0
0x20e1f7  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_array
0x20e1fc  brfalse.s loc_20E237
0x20e1fe  ldarg.0
0x20e1ff  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_array
0x20e204  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference::PinValue()
0x20e209  stloc.0
0x20e20a  ldarg.0
0x20e20b  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_array
0x20e210  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>::Value()
0x20e215  ldfld    object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray::Array
0x20e21a  ldc.i4.0
0x20e21b  ldarg.1
0x20e21c  ldarg.2
0x20e21d  ldarg.0
0x20e21e  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20e223  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x20e228  leave    loc_20E2ED
0x20e22d  ldloc.0
0x20e22e  brfalse.s loc_20E236
0x20e230  ldloc.0
0x20e231  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20e236  endfinally
0x20e237  ldarg.0
0x20e238  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_buckets
0x20e23d  callvirt instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>>::get_Count()
0x20e242  ldc.i4.1
0x20e243  sub
0x20e244  stloc.2
0x20e245  ldc.i4.0
0x20e246  stloc.s  4
0x20e248  br.s     loc_20E294
0x20e24a  ldarg.0
0x20e24b  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_buckets
0x20e250  ldloc.s  4
0x20e252  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>>::get_Item(!!T0)
0x20e257  stloc.1
0x20e258  ldloc.1
0x20e259  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference::PinValue()
0x20e25e  stloc.0
0x20e25f  ldloc.1
0x20e260  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>::Value()
0x20e265  ldfld    object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray::Array
0x20e26a  ldc.i4.0
0x20e26b  ldarg.1
0x20e26c  ldarg.2
0x20e26d  ldloc.s  4
0x20e26f  ldarg.0
0x20e270  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_bucketSize
0x20e275  mul
0x20e276  add
0x20e277  ldarg.0
0x20e278  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_bucketSize
0x20e27d  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x20e282  leave.s  loc_20E28E
0x20e284  ldloc.0
0x20e285  brfalse.s loc_20E28D
0x20e287  ldloc.0
0x20e288  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20e28d  endfinally
0x20e28e  ldloc.s  4
0x20e290  ldc.i4.1
0x20e291  add
0x20e292  stloc.s  4
0x20e294  ldloc.s  4
0x20e296  ldloc.2
0x20e297  blt.s    loc_20E24A
0x20e299  ldarg.0
0x20e29a  ldarg.0
0x20e29b  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20e2a0  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::GetIndexInBucket(int32)
0x20e2a5  stloc.3
0x20e2a6  ldloc.3
0x20e2a7  brtrue.s loc_20E2B0
0x20e2a9  ldarg.0
0x20e2aa  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_bucketSize
0x20e2af  stloc.3
0x20e2b0  ldarg.0
0x20e2b1  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_buckets
0x20e2b6  ldloc.2
0x20e2b7  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>>::get_Item(!!T0)
0x20e2bc  stloc.1
0x20e2bd  ldloc.1
0x20e2be  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference::PinValue()
0x20e2c3  stloc.0
0x20e2c4  ldloc.1
0x20e2c5  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>::Value()
0x20e2ca  ldfld    object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray::Array
0x20e2cf  ldc.i4.0
0x20e2d0  ldarg.1
0x20e2d1  ldarg.2
0x20e2d2  ldloc.2
0x20e2d3  ldarg.0
0x20e2d4  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_bucketSize
0x20e2d9  mul
0x20e2da  add
0x20e2db  ldloc.3
0x20e2dc  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x20e2e1  leave.s  loc_20E2ED
0x20e2e3  ldloc.0
0x20e2e4  brfalse.s loc_20E2EC
0x20e2e6  ldloc.0
0x20e2e7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20e2ec  endfinally
0x20e2ed  ret
```
