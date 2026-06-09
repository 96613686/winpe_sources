# HTTP_REQUEST_HANDLE_OBJECT::GenerateRawResponseHeadersForCache(CHttpHeaderParser *,char const *,ulong,uchar * *,ulong *)

- ea: `0x18007532c`
- end: `0x180075804`
- name: `?GenerateRawResponseHeadersForCache@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEAVCHttpHeaderParser@@PEBDKPEAPEAEPEAK@Z`
- size: `1240`
- prototype: `unsigned int __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this, struct CHttpHeaderParser *, const char *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180074e48`
- `0x18007580c`

## callees

- `0x180009cf0`
- `0x1800353ec`
- `0x18007532c`
- `0x18013f7b8`
- `0x180154882`
- `0x1801c9c3d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800753bb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800753bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007562a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800757e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007562a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800757e0`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180075735`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180075735`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800756e3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x1800756e3`
- `ntdll!RtlNtStatusToDosError` at `0x1800757a8`
- `ntdll!RtlNtStatusToDosError` at `0x1800757a8`

## pseudocode

```c

```
