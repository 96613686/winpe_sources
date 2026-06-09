# WaasMedic::ProtectedSettingsNamespaceMapper::IsCallerAllowedToWriteToNamespace(WaasMedic::ProtectedSettingsNamespaceMapper::tagLocationNameToSid const * const,unsigned __int64,ushort const *,bool &)

- ea: `0x180068840`
- end: `0x180068b71`
- name: `?IsCallerAllowedToWriteToNamespace@ProtectedSettingsNamespaceMapper@WaasMedic@@YAJQEBUtagLocationNameToSid@12@_KPEBGAEA_N@Z`
- size: `817`
- prototype: `__int64 __fastcall(WaasMedic::ProtectedSettingsNamespaceMapper *__hidden this, const struct WaasMedic::ProtectedSettingsNamespaceMapper::tagLocationNameToSid *const, unsigned __int64, const unsigned __int16 *, bool *)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180039e40`
- `0x18003a7d0`
- `0x1800687a4`
- `0x180068b78`

## callees

- `0x1800050c4`
- `0x180005584`
- `0x180020d88`
- `0x180028230`
- `0x18002a41c`
- `0x18002e81c`
- `0x180068840`
- `0x180068d50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800689ca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800689ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800689fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068a1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068ad7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068b1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800689fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068a1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068ad7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180068b1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068a0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068a2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068ae5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068b2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068a0b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068a2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068ae5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068b2d`

## string_xrefs

- `0x18006896c`: `GetCallerTokenAndRevertToSelf returned error. Error code: 0x%08x`
- `0x180068abd`: `IsSidInToken returned error. Error code: 0x%08x`

## pseudocode

```c

```
