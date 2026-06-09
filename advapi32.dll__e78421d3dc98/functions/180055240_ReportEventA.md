# ReportEventA

- ea: `0x180055240`
- end: `0x18005548e`
- name: `ReportEventA`
- size: `590`
- prototype: `BOOL __stdcall(HANDLE hEventLog, WORD wType, WORD wCategory, DWORD dwEventID, PSID lpUserSid, WORD wNumStrings, DWORD dwDataSize, LPCSTR *lpStrings, LPVOID lpRawData)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180035adc`
- `0x180054a68`
- `0x180055240`
- `0x180056488`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800552c2`
- `KERNEL32!HeapAlloc` at `0x1800552f6`
- `KERNEL32!HeapAlloc` at `0x1800552c2`
- `KERNEL32!HeapAlloc` at `0x1800552f6`
- `KERNEL32!GetProcessHeap` at `0x1800552b4`
- `KERNEL32!GetProcessHeap` at `0x1800552e7`
- `KERNEL32!GetProcessHeap` at `0x18005542a`
- `KERNEL32!GetProcessHeap` at `0x180055446`
- `KERNEL32!GetProcessHeap` at `0x1800552b4`
- `KERNEL32!GetProcessHeap` at `0x1800552e7`
- `KERNEL32!GetProcessHeap` at `0x18005542a`
- `KERNEL32!GetProcessHeap` at `0x180055446`
- `KERNEL32!HeapFree` at `0x180055438`
- `KERNEL32!HeapFree` at `0x180055454`
- `KERNEL32!HeapFree` at `0x180055438`
- `KERNEL32!HeapFree` at `0x180055454`
- `KERNEL32!SetLastError` at `0x180055280`
- `KERNEL32!SetLastError` at `0x180055280`

## pseudocode

```c

```
