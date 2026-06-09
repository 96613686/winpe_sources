# CWSManGroupPolicyCache::ReadString(IRequestContext *,CWSManGroupPolicyManager *,_WSMAN_POLICY_INFO const *,tagVARIANT *,WSManGroupPolicySettingState *)

- ea: `0x180041b60`
- end: `0x180041e9e`
- name: `?ReadString@CWSManGroupPolicyCache@@AEAAHPEAVIRequestContext@@PEAVCWSManGroupPolicyManager@@PEBU_WSMAN_POLICY_INFO@@PEAUtagVARIANT@@PEAW4WSManGroupPolicySettingState@@@Z`
- size: `830`
- prototype: `int(CWSManGroupPolicyCache *__hidden this, struct IRequestContext *, struct CWSManGroupPolicyManager *, const struct _WSMAN_POLICY_INFO *, struct tagVARIANT *, enum WSManGroupPolicySettingState *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180045b10`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180041b60`
- `0x180041eb0`
- `0x18004a900`
- `0x180112380`
- `0x1801123a8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041c93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041e6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041c93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041db6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041db6`
- `OLEAUT32!__imp_SysAllocString` at `0x180041e1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180041e1f`
- `OLEAUT32!__imp_SysStringLen` at `0x180041e38`
- `OLEAUT32!__imp_SysStringLen` at `0x180041e38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041d6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041d6a`

## string_xrefs

- `0x180041d4d`: `onecore\admin\wmi\wmx\binaries\service\wsmanmemory.cpp`
- `0x180041ba0`: `onecore\admin\wmi\wmx\config\wsmangrouppolicycache.cpp`

## pseudocode

```c

```
