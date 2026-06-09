# Microsoft.SharePoint.SPObjectCache`2::TrimThreadRoutineImpl

- ea: `0x560960`
- end: `0x560cf9`
- name: `Microsoft.SharePoint.SPObjectCache`2::TrimThreadRoutineImpl`
- size: `921`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x38f510`
- `0x560960`
- `0x93dab0`
- `0x93dae0`
- `0x957790`

## string_xrefs

- `0x56096f`: `The SPObjectCache trim thread has started`
- `0x56099f`: `The SPObjectCache trim thread event is null. Thread is being aborted now.`
- `0x5609c2`: `The SPObjectCache trim thread will wait for the trim thread event to signal.`
- `0x5609f3`: `The trim thread event was signaled.`
- `0x560a0e`: `The trim thread event timed out.`
- `0x560a19`: `SPObjectCache Trim Operation Scope`
- `0x560a44`: `Live object cache size in the SPObjectCache is currently {0}. High water mark size is {1}.`
- `0x560a9f`: `Total amount to trim from the SPObjectCache has been calculated to be {0} bytes.`
- `0x560aed`: `Amount trimmed from the SPObjectCache for iteration {0} is {1} bytes. Total amount trimmed thus far is {2} bytes using expire interval of {3} ms.`
- `0x560b6b`: `The expire interval for the SPObjectCache has reached an undefined interval of {0} ms. Trimming will continue with an interval of 0 ms.`
- `0x560ba6`: `The amount of bytes to trim has not been reached yet. Increasing expire interval to {0} ms.`
- `0x560bf0`: `Total amount to trim from the SPObjectCache is {0} bytes. There is still {1} bytes to trim. One more iteration will be made with an interval of 0 ms.`
- `0x560c45`: `Amount trimmed from the SPObjectCache for the final iteration was {0} bytes. Total amount trimmed is {1} bytes`
- `0x560ca3`: `The trim thread for the object cache has failed unexpectedly. The trim thread will continue again at the next interval. The following exception was thrown: {0}`
- `0x560cd5`: `The trim thread for the object cache has failed unexpectedly. The trim thread will continue again at the next interval. The following exception was thrown: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x560960  ldc.i4   0x396A3632
0x560965  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x56096a  ldc.i4   0xC8
0x56096f  ldstr    aTheSpobjectcac// "The SPObjectCache trim thread has start"...
0x560974  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x560979  ldc.i4.0
0x56097a  conv.i8
0x56097b  stloc.0
0x56097c  ldc.i4.0
0x56097d  conv.i8
0x56097e  stloc.1
0x56097f  ldc.i4.0
0x560980  conv.i8
0x560981  stloc.2
0x560982  ldc.i4.0
0x560983  conv.i8
0x560984  stloc.3
0x560985  ldc.i4.0
0x560986  stloc.s  4
0x560988  ldc.i4.0
0x560989  stloc.s  5
0x56098b  ldarg.0
0x56098c  ldfld    class [mscorlib]System.Threading.AutoResetEvent class Microsoft.SharePoint.SPObjectCache`2<var<u1>, !!T0>::trimEvent
0x560991  brtrue.s loc_5609B3
0x560993  ldc.i4   0x396A3633
0x560998  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x56099d  ldc.i4.s 0xA
0x56099f  ldstr    aTheSpobjectcac_0// "The SPObjectCache trim thread event is "...
0x5609a4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x5609a9  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x5609ae  callvirt instance void [mscorlib]System.Threading.Thread::Abort()
0x5609b3  ldc.i4   0x396A3634
0x5609b8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x5609bd  ldc.i4   0xC8
0x5609c2  ldstr    aTheSpobjectcac_1// "The SPObjectCache trim thread will wait"...
0x5609c7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x5609cc  ldarg.0
0x5609cd  ldfld    class [mscorlib]System.Threading.AutoResetEvent class Microsoft.SharePoint.SPObjectCache`2<var<u1>, !!T0>::trimEvent
0x5609d2  ldarg.0
0x5609d3  ldfld    int32 class Microsoft.SharePoint.SPObjectCache`2<var<u1>, !!T0>::checkTrimIntervalInMilliseconds
0x5609d8  ldc.i4.0
0x5609d9  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32, bool)
0x5609de  stloc.s  4
0x5609e0  ldloc.s  4
0x5609e2  brfalse.s loc_5609FF
0x5609e4  ldc.i4   0x396A3635
0x5609e9  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x5609ee  ldc.i4   0xC8
0x5609f3  ldstr    aTheTrimThreadE// "The trim thread event was signaled."
0x5609f8  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x5609fd  br.s     loc_560A18
0x5609ff  ldc.i4   0x396A3636
0x560a04  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560a09  ldc.i4   0xC8
0x560a0e  ldstr    aTheTrimThreadE_0// "The trim thread event timed out."
0x560a13  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x560a18  ldnull
0x560a19  ldstr    aSpobjectcacheT// "SPObjectCache Trim Operation Scope"
0x560a1e  newobj   instance void Microsoft.SharePoint.Administration.SPTaskUsageMonitoredScope::.ctor(class Microsoft.SharePoint.Utilities.SPDiagnosticsState state, string name)
0x560a23  stloc.s  0xD
0x560a25  ldarg.0
0x560a26  ldloca.s 0
0x560a28  ldloca.s 1
0x560a2a  ldloca.s 2
0x560a2c  ldloca.s 3
0x560a2e  ldloca.s 5
0x560a30  call     instance void class Microsoft.SharePoint.SPObjectCache`2<var<u1>, !!T0>::GetLiveItemsStatistics(int64&, int64&, int64&, int64&, int32&)
0x560a35  ldc.i4   0x396A3637
0x560a3a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560a3f  ldc.i4   0xC8
0x560a44  ldstr    aLiveObjectCach// "Live object cache size in the SPObjectC"...
0x560a49  ldc.i4.2
0x560a4a  newarr   [mscorlib]System.Object
0x560a4f  stloc.s  0xE
0x560a51  ldloc.s  0xE
0x560a53  ldc.i4.0
0x560a54  ldloca.s 0
0x560a56  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560a5b  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560a60  stelem.ref
0x560a61  ldloc.s  0xE
0x560a63  ldc.i4.1
0x560a64  ldloca.s 3
0x560a66  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560a6b  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560a70  stelem.ref
0x560a71  ldloc.s  0xE
0x560a73  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x560a78  ldloc.0
0x560a79  ldloc.3
0x560a7a  blt      loc_560C79
0x560a7f  ldc.i4.0
0x560a80  conv.i8
0x560a81  stloc.s  6
0x560a83  ldc.i4.0
0x560a84  conv.i8
0x560a85  stloc.s  7
0x560a87  ldloc.0
0x560a88  ldloc.2
0x560a89  sub
0x560a8a  stloc.s  8
0x560a8c  ldloc.s  8
0x560a8e  stloc.s  9
0x560a90  ldc.i4   0x396A3638
0x560a95  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560a9a  ldc.i4   0xC8
0x560a9f  ldstr    aTotalAmountToT// "Total amount to trim from the SPObjectC"...
0x560aa4  ldc.i4.1
0x560aa5  newarr   [mscorlib]System.Object
0x560aaa  stloc.s  0xF
0x560aac  ldloc.s  0xF
0x560aae  ldc.i4.0
0x560aaf  ldloca.s 8
0x560ab1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560ab6  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560abb  stelem.ref
0x560abc  ldloc.s  0xF
0x560abe  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x560ac3  ldc.i4.0
0x560ac4  stloc.s  0xA
0x560ac6  br       loc_560BD0
0x560acb  ldarg.0
0x560acc  ldloc.s  9
0x560ace  ldloca.s 7
0x560ad0  ldloc.s  5
0x560ad2  call     instance void class Microsoft.SharePoint.SPObjectCache`2<var<u1>, !!T0>::ExpireLiveItems(int64, int64&, int32)
0x560ad7  ldloc.s  6
0x560ad9  ldloc.s  7
0x560adb  add
0x560adc  stloc.s  6
0x560ade  ldc.i4   0x396A3639
0x560ae3  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560ae8  ldc.i4   0xC8
0x560aed  ldstr    aAmountTrimmedF// "Amount trimmed from the SPObjectCache f"...
0x560af2  ldc.i4.4
0x560af3  newarr   [mscorlib]System.Object
0x560af8  stloc.s  0x10
0x560afa  ldloc.s  0x10
0x560afc  ldc.i4.0
0x560afd  ldloca.s 0xA
0x560aff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560b04  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x560b09  stelem.ref
0x560b0a  ldloc.s  0x10
0x560b0c  ldc.i4.1
0x560b0d  ldloca.s 7
0x560b0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560b14  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560b19  stelem.ref
0x560b1a  ldloc.s  0x10
0x560b1c  ldc.i4.2
0x560b1d  ldloca.s 6
0x560b1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560b24  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560b29  stelem.ref
0x560b2a  ldloc.s  0x10
0x560b2c  ldc.i4.3
0x560b2d  ldloca.s 5
0x560b2f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560b34  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x560b39  stelem.ref
0x560b3a  ldloc.s  0x10
0x560b3c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x560b41  ldloc.s  6
0x560b43  ldloc.s  8
0x560b45  blt.s    loc_560B4D
0x560b47  ldc.i4.0
0x560b48  conv.i8
0x560b49  stloc.s  9
0x560b4b  br.s     loc_560B54
0x560b4d  ldloc.s  8
0x560b4f  ldloc.s  6
0x560b51  sub
0x560b52  stloc.s  9
0x560b54  ldc.i4.0
0x560b55  conv.i8
0x560b56  ldloc.s  9
0x560b58  beq.s    loc_560BD8
0x560b5a  ldc.i4.2
0x560b5b  ldloc.s  5
0x560b5d  ble.s    loc_560B91
0x560b5f  ldc.i4   0x396A3661
0x560b64  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560b69  ldc.i4.s 0xA
0x560b6b  ldstr    aTheExpireInter// "The expire interval for the SPObjectCac"...
0x560b70  ldc.i4.1
0x560b71  newarr   [mscorlib]System.Object
0x560b76  stloc.s  0x11
0x560b78  ldloc.s  0x11
0x560b7a  ldc.i4.0
0x560b7b  ldloca.s 5
0x560b7d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560b82  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x560b87  stelem.ref
0x560b88  ldloc.s  0x11
0x560b8a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x560b8f  br.s     loc_560BD8
0x560b91  ldloc.s  5
0x560b93  ldc.i4.2
0x560b94  div
0x560b95  stloc.s  5
0x560b97  ldc.i4   0x396A3662
0x560b9c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560ba1  ldc.i4   0xC8
0x560ba6  ldstr    aTheAmountOfByt// "The amount of bytes to trim has not bee"...
0x560bab  ldc.i4.1
0x560bac  newarr   [mscorlib]System.Object
0x560bb1  stloc.s  0x12
0x560bb3  ldloc.s  0x12
0x560bb5  ldc.i4.0
0x560bb6  ldloca.s 5
0x560bb8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560bbd  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x560bc2  stelem.ref
0x560bc3  ldloc.s  0x12
0x560bc5  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x560bca  ldloc.s  0xA
0x560bcc  ldc.i4.1
0x560bcd  add
0x560bce  stloc.s  0xA
0x560bd0  ldloc.s  0xA
0x560bd2  ldc.i4.5
0x560bd3  blt      loc_560ACB
0x560bd8  ldc.i4.0
0x560bd9  conv.i8
0x560bda  ldloc.s  9
0x560bdc  beq      loc_560C79
0x560be1  ldc.i4   0x396A3663
0x560be6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560beb  ldc.i4   0xC8
0x560bf0  ldstr    aTotalAmountToT_0// "Total amount to trim from the SPObjectC"...
0x560bf5  ldc.i4.2
0x560bf6  newarr   [mscorlib]System.Object
0x560bfb  stloc.s  0x13
0x560bfd  ldloc.s  0x13
0x560bff  ldc.i4.0
0x560c00  ldloca.s 8
0x560c02  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560c07  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560c0c  stelem.ref
0x560c0d  ldloc.s  0x13
0x560c0f  ldc.i4.1
0x560c10  ldloca.s 9
0x560c12  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560c17  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560c1c  stelem.ref
0x560c1d  ldloc.s  0x13
0x560c1f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x560c24  ldarg.0
0x560c25  ldloc.s  9
0x560c27  ldloca.s 7
0x560c29  ldc.i4.0
0x560c2a  call     instance void class Microsoft.SharePoint.SPObjectCache`2<var<u1>, !!T0>::ExpireLiveItems(int64, int64&, int32)
0x560c2f  ldloc.s  6
0x560c31  ldloc.s  7
0x560c33  add
0x560c34  stloc.s  6
0x560c36  ldc.i4   0x396A3664
0x560c3b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560c40  ldc.i4   0xC8
0x560c45  ldstr    aAmountTrimmedF_0// "Amount trimmed from the SPObjectCache f"...
0x560c4a  ldc.i4.2
0x560c4b  newarr   [mscorlib]System.Object
0x560c50  stloc.s  0x14
0x560c52  ldloc.s  0x14
0x560c54  ldc.i4.0
0x560c55  ldloca.s 7
0x560c57  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560c5c  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560c61  stelem.ref
0x560c62  ldloc.s  0x14
0x560c64  ldc.i4.1
0x560c65  ldloca.s 6
0x560c67  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x560c6c  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x560c71  stelem.ref
0x560c72  ldloc.s  0x14
0x560c74  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x560c79  ldarg.0
0x560c7a  call     instance void class Microsoft.SharePoint.SPObjectCache`2<var<u1>, !!T0>::RemoveGarbageCollectedItems()
0x560c7f  leave.s  loc_560C8D
0x560c81  ldloc.s  0xD
0x560c83  brfalse.s loc_560C8C
0x560c85  ldloc.s  0xD
0x560c87  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x560c8c  endfinally
0x560c8d  leave    loc_560979
0x560c92  stloc.s  0xB
0x560c94  ldc.i4   0x6432616F
0x560c99  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ObjectCache()
0x560c9e  ldc.i4   0xC8
0x560ca3  ldstr    aTheTrimThreadF// "The trim thread for the object cache ha"...
0x560ca8  ldc.i4.1
0x560ca9  newarr   [mscorlib]System.Object
0x560cae  stloc.s  0x15
0x560cb0  ldloc.s  0x15
0x560cb2  ldc.i4.0
0x560cb3  ldloc.s  0xB
0x560cb5  callvirt instance string [mscorlib]System.Object::ToString()
0x560cba  stelem.ref
  ... truncated ...
```
