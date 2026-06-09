# CInterceptor_IWbemSyncProvider::Helper_QueryInstancesAsync(IWbemHiPerfProvider *,ushort * const,long,IWbemContext *,IWbemObjectSink *)

- ea: `0x14000d2c4`
- end: `0x14000d5f5`
- name: `?Helper_QueryInstancesAsync@CInterceptor_IWbemSyncProvider@@AEAAJPEAUIWbemHiPerfProvider@@QEAGJPEAUIWbemContext@@PEAUIWbemObjectSink@@@Z`
- size: `817`
- prototype: `int(CInterceptor_IWbemSyncProvider *__hidden this, struct IWbemHiPerfProvider *, unsigned __int16 *const, int, struct IWbemContext *, struct IWbemObjectSink *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c3a0`
- `0x140028ef0`

## callees

- `0x14000a530`
- `0x14000d1e0`
- `0x14000d2c4`
- `0x14000e8a0`
- `0x1400234b8`
- `0x140048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x14000d5b8`
- `wbemcomn!GetMemLogObject` at `0x14000d5b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000d5c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000d5c3`
- `OLEAUT32!__imp_SysAllocString` at `0x14000d3cc`
- `OLEAUT32!__imp_SysAllocString` at `0x14000d3cc`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d463`
- `OLEAUT32!__imp_SysFreeString` at `0x14000d463`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000d442`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000d574`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000d442`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000d574`

## pseudocode

```c

```
