# CoInternetQueryInfo

- ea: `0x1800188f0`
- end: `0x180018d06`
- name: `CoInternetQueryInfo`
- size: `1046`
- prototype: `HRESULT __stdcall(LPCWSTR pwzUrl, QUERYOPTION QueryOptions, DWORD dwQueryFlags, LPVOID pvBuffer, DWORD cbBuffer, DWORD *pcbBuffer, DWORD dwReserved)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18010fef8`

## callees

- `0x1800150e0`
- `0x18001511c`
- `0x1800188f0`
- `0x180018e90`
- `0x18001946c`
- `0x1800214d0`
- `0x18002c428`
- `0x180030880`
- `0x180111864`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800189ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800189ef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001893f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001893f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180018bf7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180018bf7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018c45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180018c45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018c6f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c5d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018c5d`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x180018b23`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x180018b23`
- `WININET!GetUrlCacheEntryInfoExW` at `0x180018c26`
- `WININET!GetUrlCacheEntryInfoExW` at `0x180018c26`

## pseudocode

```c

```
