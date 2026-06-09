# Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::ClearCache

- ea: `0x44f40`
- end: `0x44fa6`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::ClearCache`
- size: `102`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3faa0`
- `0x41750`
- `0x45030`
- `0x45500`

## callees

- `0x1cd50`
- `0x1ce20`
- `0x44f40`

## string_xrefs

- `0x44f41`: `ClearCache`
- `0x44f9b`: `ClearCache`

## pseudocode

```c

```

## disassembly

```asm
0x44f40  ldarg.0
0x44f41  ldstr    aClearcache// "ClearCache"
0x44f46  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(object thisObject, string methodName)
0x44f4b  ldarg.0
0x44f4c  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::liteEventsWithEventHandles
0x44f51  callvirt instance void [mscorlib]System.Collections.Hashtable::Clear()
0x44f56  ldarg.0
0x44f57  ldc.i4.0
0x44f58  stfld    bool Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::allEventsInCache
0x44f5d  ldarg.0
0x44f5e  ldc.i4.0
0x44f5f  conv.i8
0x44f60  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::firstEventInCache
0x44f65  ldarg.0
0x44f66  ldc.i4.0
0x44f67  conv.i8
0x44f68  stfld    unsigned int64 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::firstItemIndexInLiteCache
0x44f6d  ldarg.0
0x44f6e  ldc.i4.0
0x44f6f  stfld    int32 Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::countOfItemsInCache
0x44f74  ldc.i4.0
0x44f75  stloc.0
0x44f76  br.s     loc_44F8F
0x44f78  ldarg.0
0x44f79  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord[] Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::_lstLiteRecords
0x44f7e  ldloc.0
0x44f7f  ldelem.ref
0x44f80  brfalse.s loc_44F8B
0x44f82  ldarg.0
0x44f83  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord[] Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::_lstLiteRecords
0x44f88  ldloc.0
0x44f89  ldnull
0x44f8a  stelem.ref
0x44f8b  ldloc.0
0x44f8c  ldc.i4.1
0x44f8d  add
0x44f8e  stloc.0
0x44f8f  ldloc.0
0x44f90  ldarg.0
0x44f91  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.LiteEventRecord[] Microsoft.Windows.ManagementUI.CombinedControls.LiteRecordCache::_lstLiteRecords
0x44f96  ldlen
0x44f97  conv.i4
0x44f98  blt.s    loc_44F78
0x44f9a  ldarg.0
0x44f9b  ldstr    aClearcache// "ClearCache"
0x44fa0  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(object thisObject, string methodName)
0x44fa5  ret
```
