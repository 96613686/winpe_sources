# ATL::CComCoClass<CDsmRefreshTask,&_GUID const CLSID_DsmRefreshTask>::GetObjectDescription(void)

- ea: `0x180009790`
- end: `0x180009793`
- name: `?GetObjectDescription@?$CComCoClass@VCDsmRefreshTask@@$1?CLSID_DsmRefreshTask@@3U_GUID@@B@ATL@@SAPEBGXZ`
- size: `3`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800019e8`

## pseudocode

```c
__int64 ATL::CComCoClass<CDsmRefreshTask,&_GUID const CLSID_DsmRefreshTask>::GetObjectDescription()
{
  return 0;
}

```

## disassembly

```asm
0x180009790  xor     eax, eax
0x180009792  retn
```
