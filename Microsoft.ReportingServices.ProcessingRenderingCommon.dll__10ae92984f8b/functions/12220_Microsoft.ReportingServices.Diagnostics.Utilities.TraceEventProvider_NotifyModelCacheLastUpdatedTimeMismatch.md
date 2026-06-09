# Microsoft.ReportingServices.Diagnostics.Utilities.TraceEventProvider::NotifyModelCacheLastUpdatedTimeMismatch

- ea: `0x12220`
- end: `0x1224d`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.TraceEventProvider::NotifyModelCacheLastUpdatedTimeMismatch`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x12226`: `Method {0}: cacheEntryHasLastUpdatedTime={1}, requestHasLastUpdatedTime={2}`

## pseudocode

```c

```

## disassembly

```asm
0x12220  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x12225  ldc.i4.1
0x12226  ldstr    aMethod0Cacheen// "Method {0}: cacheEntryHasLastUpdatedTim"...
0x1222b  ldc.i4.3
0x1222c  newarr   [mscorlib]System.Object
0x12231  dup
0x12232  ldc.i4.0
0x12233  ldarg.1
0x12234  stelem.ref
0x12235  dup
0x12236  ldc.i4.1
0x12237  ldarg.2
0x12238  box      [mscorlib]System.Boolean
0x1223d  stelem.ref
0x1223e  dup
0x1223f  ldc.i4.2
0x12240  ldarg.3
0x12241  box      [mscorlib]System.Boolean
0x12246  stelem.ref
0x12247  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1224c  ret
```
