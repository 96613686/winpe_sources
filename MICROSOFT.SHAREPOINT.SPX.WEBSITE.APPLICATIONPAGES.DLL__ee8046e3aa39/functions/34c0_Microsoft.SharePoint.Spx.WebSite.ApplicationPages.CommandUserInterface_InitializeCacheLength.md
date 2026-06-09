# Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CommandUserInterface::InitializeCacheLength

- ea: `0x34c0`
- end: `0x34db`
- name: `Microsoft.SharePoint.Spx.WebSite.ApplicationPages.CommandUserInterface::InitializeCacheLength`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3770`

## callees

- `0x34c0`

## string_xrefs

- `0x34c0`: `CUIDataCacheLength`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  ldstr    aCuidatacachele// "CUIDataCacheLength"
0x34c5  call     string [Microsoft.SharePoint.Spx]Microsoft.SharePoint.Spx.WebConfigManager::GetConfigData(string)
0x34ca  ldloca.s 0
0x34cc  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x34d1  brtrue.s loc_34D9
0x34d3  ldc.i4   0x16D
0x34d8  stloc.0
0x34d9  ldloc.0
0x34da  ret
```
