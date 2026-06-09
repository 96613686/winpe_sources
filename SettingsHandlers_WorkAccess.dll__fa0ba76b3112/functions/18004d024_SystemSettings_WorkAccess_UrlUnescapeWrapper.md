# SystemSettings::WorkAccess::UrlUnescapeWrapper

- ea: `0x18004d024`
- end: `0x18004d14a`
- name: `SystemSettings::WorkAccess::UrlUnescapeWrapper`
- size: `294`
- prototype: `__int64 __fastcall(PWSTR pszUrl)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800476b8`

## callees

- `0x1800096ec`
- `0x18004d024`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d071`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d105`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d071`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d105`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d0c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d0ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d057`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d0c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004d0ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d0db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d0db`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x18004d08e`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x18004d122`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x18004d08e`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x18004d122`

## string_xrefs

- `0x18004d0b1`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmenthelper.cpp`

## pseudocode

```c

```
