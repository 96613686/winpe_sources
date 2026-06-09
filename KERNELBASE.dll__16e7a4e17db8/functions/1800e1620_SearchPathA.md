# SearchPathA

- ea: `0x1800e1620`
- end: `0x1800e18c7`
- name: `SearchPathA`
- size: `679`
- prototype: `DWORD __stdcall(LPCSTR lpPath, LPCSTR lpFileName, LPCSTR lpExtension, DWORD nBufferLength, LPSTR lpBuffer, LPSTR *lpFilePart)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18013e9a0`

## callees

- `0x1800134a0`
- `0x18006e590`
- `0x1800e1620`
- `0x1800e19d0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800e16bb`
- `ntdll!RtlFreeUnicodeString` at `0x1800e16c5`
- `ntdll!RtlFreeUnicodeString` at `0x1800e1894`
- `ntdll!RtlFreeUnicodeString` at `0x1800e18a3`
- `ntdll!RtlFreeUnicodeString` at `0x1800e18ad`
- `ntdll!RtlFreeUnicodeString` at `0x1800e16bb`
- `ntdll!RtlFreeUnicodeString` at `0x1800e16c5`
- `ntdll!RtlFreeUnicodeString` at `0x1800e1894`
- `ntdll!RtlFreeUnicodeString` at `0x1800e18a3`
- `ntdll!RtlFreeUnicodeString` at `0x1800e18ad`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800e1819`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800e1819`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e17b8`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e17e1`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e1858`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e17b8`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e17e1`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e1858`
- `ntdll!RtlFreeHeap` at `0x1800e1746`
- `ntdll!RtlFreeHeap` at `0x1800e1885`
- `ntdll!RtlFreeHeap` at `0x1800e1746`
- `ntdll!RtlFreeHeap` at `0x1800e1885`
- `ntdll!RtlAllocateHeap` at `0x1800e16ea`
- `ntdll!RtlAllocateHeap` at `0x1800e1766`
- `ntdll!RtlAllocateHeap` at `0x1800e16ea`
- `ntdll!RtlAllocateHeap` at `0x1800e1766`

## pseudocode

```c

```
