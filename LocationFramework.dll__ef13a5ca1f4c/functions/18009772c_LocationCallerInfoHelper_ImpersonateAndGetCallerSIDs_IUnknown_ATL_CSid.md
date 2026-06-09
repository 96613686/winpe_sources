# LocationCallerInfoHelper::ImpersonateAndGetCallerSIDs(IUnknown *,ATL::CSid &)

- ea: `0x18009772c`
- end: `0x1800977fb`
- name: `?ImpersonateAndGetCallerSIDs@LocationCallerInfoHelper@@SAJPEAUIUnknown@@AEAVCSid@ATL@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(struct IUnknown *, struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054da0`

## callees

- `0x180018228`
- `0x18001e170`
- `0x18001f09c`
- `0x18009772c`
- `0x1800a98c0`

## import_xrefs

- `combase!__imp_CoImpersonateClientOfObject` at `0x18009775a`
- `combase!__imp_CoImpersonateClientOfObject` at `0x18009775a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18009776e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800977d7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18009776e`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800977d7`

## pseudocode

```c

```
