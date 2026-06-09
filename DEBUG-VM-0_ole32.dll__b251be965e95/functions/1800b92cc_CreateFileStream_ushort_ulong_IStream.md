# CreateFileStream(ushort *,ulong,IStream * *)

- ea: `0x1800b92cc`
- end: `0x1800b9442`
- name: `?CreateFileStream@@YAJPEAGKPEAPEAUIStream@@@Z`
- size: `374`
- prototype: `HRESULT __fastcall(wchar_t *bstrFile, unsigned int stgm, IStream **ppstrm)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800b9880`
- `0x1800b99b0`

## callees

- `0x180052390`
- `0x180053014`
- `0x1800b9274`
- `0x1800b92cc`
- `0x1800b9448`
- `0x1800b9488`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b941c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b941c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b9348`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b93dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b9348`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b93dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b93bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b9390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b93bf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b9334`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b9386`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b9334`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800b9386`
- `api-ms-win-core-kernel32-private-l1-1-0!_lclose` at `0x1800b940a`
- `api-ms-win-core-kernel32-private-l1-1-0!_lclose` at `0x1800b940a`

## pseudocode

```c

```
