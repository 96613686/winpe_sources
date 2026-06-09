# Microsoft.ReportingServices.Library.DbConnectionPoolLruCache::AddConnectionEntry

- ea: `0xb320`
- end: `0xb3b9`
- name: `Microsoft.ReportingServices.Library.DbConnectionPoolLruCache::AddConnectionEntry`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xaff0`
- `0x128a0`

## callees

- `0x3d0`
- `0xb320`
- `0x87a90`

## string_xrefs

- `0xb353`: `LRU cache capacity complete with duration={0}`
- `0xb38c`: `Eviction of {0} connections completed with duration={1}`

## pseudocode

```c

```

## disassembly

```asm
0xb320  newobj   instance void <>c__DisplayClass4_0::.ctor()
0xb325  stloc.0
0xb326  ldloc.0
0xb327  ldarg.0
0xb328  stfld    class Microsoft.ReportingServices.Library.ConnectionEntry <>c__DisplayClass4_0::connectionEntry
0xb32d  ldloc.0
0xb32e  ldarg.1
0xb32f  stfld    bool <>c__DisplayClass4_0::closeEvictedConnectionsAsync
0xb334  ldloc.0
0xb335  ldnull
0xb336  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry> <>c__DisplayClass4_0::connectionsToClose
0xb33b  ldloc.0
0xb33c  ldftn    instance void <>c__DisplayClass4_0::<AddConnectionEntry>b__0()
0xb342  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xb347  call     int64 Microsoft.ReportingServices.Diagnostics.Utilities.PerformanceUtilities::ExecuteAndMeasureDurationMs(class [mscorlib]System.Action action)
0xb34c  stloc.1
0xb34d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0xb352  ldc.i4.3
0xb353  ldstr    aLruCacheCapaci// "LRU cache capacity complete with durati"...
0xb358  ldc.i4.1
0xb359  newarr   [mscorlib]System.Object
0xb35e  dup
0xb35f  ldc.i4.0
0xb360  ldloc.1
0xb361  box      [mscorlib]System.Int64
0xb366  stelem.ref
0xb367  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xb36c  ldloc.0
0xb36d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry> <>c__DisplayClass4_0::connectionsToClose
0xb372  brfalse.s loc_B3B8
0xb374  ldloc.0
0xb375  ldftn    instance void <>c__DisplayClass4_0::<AddConnectionEntry>b__1()
0xb37b  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xb380  call     int64 Microsoft.ReportingServices.Diagnostics.Utilities.PerformanceUtilities::ExecuteAndMeasureDurationMs(class [mscorlib]System.Action action)
0xb385  stloc.2
0xb386  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DataExtensionTracer()
0xb38b  ldc.i4.3
0xb38c  ldstr    aEvictionOf0Con// "Eviction of {0} connections completed w"...
0xb391  ldc.i4.2
0xb392  newarr   [mscorlib]System.Object
0xb397  dup
0xb398  ldc.i4.0
0xb399  ldloc.0
0xb39a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry> <>c__DisplayClass4_0::connectionsToClose
0xb39f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ConnectionEntry>::get_Count()
0xb3a4  box      [mscorlib]System.Int32
0xb3a9  stelem.ref
0xb3aa  dup
0xb3ab  ldc.i4.1
0xb3ac  ldloc.2
0xb3ad  box      [mscorlib]System.Int64
0xb3b2  stelem.ref
0xb3b3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xb3b8  ret
```
