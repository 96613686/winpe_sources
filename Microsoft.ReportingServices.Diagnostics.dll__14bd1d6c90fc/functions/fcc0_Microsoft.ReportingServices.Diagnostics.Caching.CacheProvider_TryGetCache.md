# Microsoft.ReportingServices.Diagnostics.Caching.CacheProvider::TryGetCache

- ea: `0xfcc0`
- end: `0xfcdd`
- name: `Microsoft.ReportingServices.Diagnostics.Caching.CacheProvider::TryGetCache`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xfcb0`

## callees

- `0xfcc0`
- `0xfd80`

## pseudocode

```c

```

## disassembly

```asm
0xfcc0  ldarg.1
0xfcc1  ldnull
0xfcc2  stind.ref
0xfcc3  ldsfld   class Microsoft.ReportingServices.Diagnostics.Caching.ICacheFactory Microsoft.ReportingServices.Diagnostics.Caching.CacheProvider::m_cacheFactory
0xfcc8  brfalse.s loc_FCD7
0xfcca  ldarg.1
0xfccb  ldsfld   class Microsoft.ReportingServices.Diagnostics.Caching.ICacheFactory Microsoft.ReportingServices.Diagnostics.Caching.CacheProvider::m_cacheFactory
0xfcd0  ldarg.0
0xfcd1  callvirt instance class Microsoft.ReportingServices.Diagnostics.Caching.ICache Microsoft.ReportingServices.Diagnostics.Caching.ICacheFactory::CreateCache(valuetype Microsoft.ReportingServices.Diagnostics.Caching.CacheIdentifier cacheId)
0xfcd6  stind.ref
0xfcd7  ldarg.1
0xfcd8  ldind.ref
0xfcd9  ldnull
0xfcda  cgt.un
0xfcdc  ret
```
