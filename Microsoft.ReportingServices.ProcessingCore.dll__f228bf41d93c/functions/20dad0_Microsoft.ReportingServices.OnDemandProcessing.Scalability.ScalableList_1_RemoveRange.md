# Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1::RemoveRange

- ea: `0x20dad0`
- end: `0x20dcc6`
- name: `Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1::RemoveRange`
- size: `502`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x20b4f0`
- `0x20dad0`

## string_xrefs

- `0x20dad1`: `RemoveRange`
- `0x20dae5`: `ScalableList.RemoveRange: Index may not be less than 0`
- `0x20daf9`: `ScalableList.RemoveRange: Count may not be less than 0`
- `0x20db14`: `ScalableList.RemoveRange: Index + Count may not be larger than the number of elements in the list`

## pseudocode

```c

```

## disassembly

```asm
0x20dad0  ldarg.0
0x20dad1  ldstr    aRemoverange// "RemoveRange"
0x20dad6  call     instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::CheckReadOnly(string)
0x20dadb  ldarg.1
0x20dadc  ldc.i4.0
0x20dadd  bge.s    loc_20DAEF
0x20dadf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20dae4  ldc.i4.0
0x20dae5  ldstr    aScalablelistRe// "ScalableList.RemoveRange: Index may not"...
0x20daea  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20daef  ldarg.2
0x20daf0  ldc.i4.0
0x20daf1  bge.s    loc_20DB03
0x20daf3  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20daf8  ldc.i4.0
0x20daf9  ldstr    aScalablelistRe_0// "ScalableList.RemoveRange: Count may not"...
0x20dafe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20db03  ldarg.1
0x20db04  ldarg.2
0x20db05  add
0x20db06  ldarg.0
0x20db07  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::get_Count()
0x20db0c  ble.s    loc_20DB1E
0x20db0e  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x20db13  ldc.i4.0
0x20db14  ldstr    aScalablelistRe_1// "ScalableList.RemoveRange: Index + Count"...
0x20db19  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x20db1e  ldarg.0
0x20db1f  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_array
0x20db24  brfalse.s loc_20DB76
0x20db26  ldarg.0
0x20db27  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_array
0x20db2c  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference::PinValue()
0x20db31  stloc.0
0x20db32  ldarg.0
0x20db33  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_array
0x20db38  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>::Value()
0x20db3d  ldfld    object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray::Array
0x20db42  stloc.1
0x20db43  ldloc.1
0x20db44  ldlen
0x20db45  conv.i4
0x20db46  ldarg.2
0x20db47  sub
0x20db48  ldarg.1
0x20db49  sub
0x20db4a  stloc.2
0x20db4b  ldloc.1
0x20db4c  ldarg.1
0x20db4d  ldarg.2
0x20db4e  add
0x20db4f  ldloc.1
0x20db50  ldarg.1
0x20db51  ldloc.2
0x20db52  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x20db57  leave.s  loc_20DB63
0x20db59  ldloc.0
0x20db5a  brfalse.s loc_20DB62
0x20db5c  ldloc.0
0x20db5d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20db62  endfinally
0x20db63  ldarg.0
0x20db64  ldarg.0
0x20db65  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20db6a  ldarg.2
0x20db6b  sub
0x20db6c  stfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20db71  br       loc_20DCB7
0x20db76  ldarg.1
0x20db77  ldarg.2
0x20db78  add
0x20db79  stloc.3
0x20db7a  ldarg.1
0x20db7b  stloc.s  4
0x20db7d  ldarg.0
0x20db7e  ldloc.3
0x20db7f  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::GetIndexInBucket(int32)
0x20db84  stloc.s  7
0x20db86  ldarg.0
0x20db87  ldloc.s  4
0x20db89  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::GetIndexInBucket(int32)
0x20db8e  stloc.s  8
0x20db90  ldarg.0
0x20db91  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_bucketSize
0x20db96  ldloc.s  8
0x20db98  sub
0x20db99  ldarg.0
0x20db9a  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_bucketSize
0x20db9f  ldloc.s  7
0x20dba1  sub
0x20dba2  ldarg.0
0x20dba3  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20dba8  ldloc.3
0x20dba9  sub
0x20dbaa  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x20dbaf  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x20dbb4  stloc.s  9
0x20dbb6  ldloc.s  9
0x20dbb8  ldc.i4.0
0x20dbb9  ble      loc_20DC48
0x20dbbe  ldarg.0
0x20dbbf  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_buckets
0x20dbc4  ldarg.0
0x20dbc5  ldloc.s  4
0x20dbc7  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::GetBucketIndex(int32)
0x20dbcc  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>>::get_Item(!!T0)
0x20dbd1  stloc.s  0xA
0x20dbd3  ldarg.0
0x20dbd4  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_buckets
0x20dbd9  ldarg.0
0x20dbda  ldloc.3
0x20dbdb  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::GetBucketIndex(int32)
0x20dbe0  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>>::get_Item(!!T0)
0x20dbe5  stloc.s  0xB
0x20dbe7  ldloc.s  0xA
0x20dbe9  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference::PinValue()
0x20dbee  stloc.0
0x20dbef  ldloc.s  0xB
0x20dbf1  callvirt instance class [mscorlib]System.IDisposable Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference::PinValue()
0x20dbf6  stloc.s  0xC
0x20dbf8  ldloc.s  0xB
0x20dbfa  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>::Value()
0x20dbff  ldfld    object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray::Array
0x20dc04  ldloc.s  0xA
0x20dc06  callvirt instance var<u1> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>::Value()
0x20dc0b  ldfld    object[] Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray::Array
0x20dc10  stloc.s  0xD
0x20dc12  ldloc.s  7
0x20dc14  ldloc.s  0xD
0x20dc16  ldloc.s  8
0x20dc18  ldloc.s  9
0x20dc1a  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x20dc1f  leave.s  loc_20DC37
0x20dc21  ldloc.s  0xC
0x20dc23  brfalse.s loc_20DC2C
0x20dc25  ldloc.s  0xC
0x20dc27  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20dc2c  endfinally
0x20dc2d  ldloc.0
0x20dc2e  brfalse.s loc_20DC36
0x20dc30  ldloc.0
0x20dc31  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20dc36  endfinally
0x20dc37  ldloc.s  4
0x20dc39  ldloc.s  9
0x20dc3b  add
0x20dc3c  stloc.s  4
0x20dc3e  ldloc.3
0x20dc3f  ldloc.s  9
0x20dc41  add
0x20dc42  stloc.3
0x20dc43  br       loc_20DB7D
0x20dc48  ldarg.0
0x20dc49  ldarg.0
0x20dc4a  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20dc4f  ldarg.2
0x20dc50  sub
0x20dc51  stfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20dc56  ldarg.0
0x20dc57  ldarg.0
0x20dc58  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20dc5d  call     instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::GetBucketIndex(int32)
0x20dc62  stloc.s  5
0x20dc64  ldarg.0
0x20dc65  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_count
0x20dc6a  ldarg.0
0x20dc6b  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_bucketSize
0x20dc70  rem
0x20dc71  brtrue.s loc_20DC77
0x20dc73  ldloc.s  5
0x20dc75  brtrue.s loc_20DC7D
0x20dc77  ldloc.s  5
0x20dc79  ldc.i4.1
0x20dc7a  add
0x20dc7b  stloc.s  5
0x20dc7d  ldarg.0
0x20dc7e  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_buckets
0x20dc83  callvirt instance int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>>::get_Count()
0x20dc88  ldloc.s  5
0x20dc8a  sub
0x20dc8b  stloc.s  6
0x20dc8d  ldloc.s  6
0x20dc8f  ldc.i4.0
0x20dc90  ble.s    loc_20DCB7
0x20dc92  ldarg.0
0x20dc93  ldfld    class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>> class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_buckets
0x20dc98  ldloc.s  5
0x20dc9a  ldloc.s  6
0x20dc9c  callvirt instance void class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.IReference`1<class Microsoft.ReportingServices.OnDemandProcessing.Scalability.StorableArray>>::RemoveRange(int32, int32)
0x20dca1  ldarg.0
0x20dca2  ldarg.0
0x20dca3  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_capacity
0x20dca8  ldloc.s  6
0x20dcaa  ldarg.0
0x20dcab  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_bucketSize
0x20dcb0  mul
0x20dcb1  sub
0x20dcb2  stfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_capacity
0x20dcb7  ldarg.0
0x20dcb8  ldarg.0
0x20dcb9  ldfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_version
0x20dcbe  ldc.i4.1
0x20dcbf  add
0x20dcc0  stfld    int32 class Microsoft.ReportingServices.OnDemandProcessing.Scalability.ScalableList`1<var<u1>>::m_version
0x20dcc5  ret
```
