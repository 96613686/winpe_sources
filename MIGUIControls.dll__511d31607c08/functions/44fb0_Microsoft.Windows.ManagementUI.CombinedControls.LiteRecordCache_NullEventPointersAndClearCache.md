# Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::NullEventPointersAndClearCache

- ea: `0x44fb0`
- end: `0x45023`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::NullEventPointersAndClearCache`
- size: `115`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x401e0`
- `0x413f0`
- `0x414a0`

## callees

- `0x1cd50`
- `0x1ce20`
- `0x3a660`
- `0x44fb0`

## string_xrefs

- `0x44fb1`: `ClearCache`
- `0x45018`: `ClearCache`

## pseudocode

```c

```

## disassembly

```asm
0x44fb0  ldarg.0
0x44fb1  ldstr    aClearcache// "ClearCache"
0x44fb6  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x44fbb  ldarg.0
0x44fbc  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::liteEventsWithEventHandles
0x44fc1  callvirt instance void [mscorlib]System.Collections.Hashtable::Clear()
0x44fc6  ldarg.0
0x44fc7  ldc.i4.0
0x44fc8  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::allEventsInCache
0x44fcd  ldarg.0
0x44fce  ldc.i4.0
0x44fcf  conv.i8
0x44fd0  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::firstEventInCache
0x44fd5  ldarg.0
0x44fd6  ldc.i4.0
0x44fd7  conv.i8
0x44fd8  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::firstItemIndexInLiteCache
0x44fdd  ldarg.0
0x44fde  ldc.i4.0
0x44fdf  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::countOfItemsInCache
0x44fe4  ldc.i4.0
0x44fe5  stloc.0
0x44fe6  br.s     loc_4500C
0x44fe8  ldarg.0
0x44fe9  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord[] Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::_lstLiteRecords
0x44fee  ldloc.0
0x44fef  ldelem.ref
0x44ff0  brfalse.s loc_45008
0x44ff2  ldarg.0
0x44ff3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord[] Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::_lstLiteRecords
0x44ff8  ldloc.0
0x44ff9  ldelem.ref
0x44ffa  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord::Dispose()
0x44fff  ldarg.0
0x45000  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord[] Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::_lstLiteRecords
0x45005  ldloc.0
0x45006  ldnull
0x45007  stelem.ref
0x45008  ldloc.0
0x45009  ldc.i4.1
0x4500a  add
0x4500b  stloc.0
0x4500c  ldloc.0
0x4500d  ldarg.0
0x4500e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord[] Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::_lstLiteRecords
0x45013  ldlen
0x45014  conv.i4
0x45015  blt.s    loc_44FE8
0x45017  ldarg.0
0x45018  ldstr    aClearcache// "ClearCache"
0x4501d  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x45022  ret
```
