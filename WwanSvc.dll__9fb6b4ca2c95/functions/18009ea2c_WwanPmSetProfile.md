# WwanPmSetProfile

- ea: `0x18009ea2c`
- end: `0x18009eec2`
- name: `WwanPmSetProfile`
- size: `1174`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, unsigned int *, enum WWAN_PROFILE_INVALID_REASON *)`
- caller_count: `5`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180037ea8`
- `0x18003cfd8`
- `0x180084690`
- `0x18009c308`
- `0x18009e354`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x18000f0f4`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x18009b6c8`
- `0x18009bae8`
- `0x18009bba0`
- `0x18009c608`
- `0x18009e6dc`
- `0x18009ea2c`
- `0x1800a3e84`
- `0x1800a4e14`
- `0x1800b6ac0`
- `0x1800c8520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009eb06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ed5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009edda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009eb06`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009ed5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009edda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ed79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009edf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ee6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ed79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009edf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009ee6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ebfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ec34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ebfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ec34`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18009ec4f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18009ec4f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009ee4b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009ee4b`
- `WwanPrfl!WwanProfileCleanup` at `0x18009ee55`
- `WwanPrfl!WwanProfileCleanup` at `0x18009ee55`
- `WwanPrfl!WwanProfileInit` at `0x18009eb19`
- `WwanPrfl!WwanProfileInit` at `0x18009eb19`
- `WwanPrfl!WwanProfileDeinit` at `0x18009ee5f`
- `WwanPrfl!WwanProfileDeinit` at `0x18009ee5f`

## string_xrefs

- `0x18009eacb`: `profile XML to be set:\n %ws`
- `0x18009eb70`: `Invalid XML, errCode (0x%8x)`
- `0x18009ecdf`: `Profile overwrite failed, errCode (0x%8x)`

## pseudocode

```c

```
