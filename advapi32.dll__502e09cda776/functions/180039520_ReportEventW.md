# ReportEventW

- ea: `0x180039520`
- end: `0x18003973a`
- name: `ReportEventW`
- size: `538`
- prototype: `BOOL __stdcall(HANDLE hEventLog, WORD wType, WORD wCategory, DWORD dwEventID, PSID lpUserSid, WORD wNumStrings, DWORD dwDataSize, LPCWSTR *lpStrings, LPVOID lpRawData)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18004a2d0`

## callees

- `0x180036bf4`
- `0x1800383a4`
- `0x180039520`
- `0x180039740`
- `0x1800607b0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800395ad`
- `KERNEL32!HeapAlloc` at `0x1800395e4`
- `KERNEL32!HeapAlloc` at `0x1800395ad`
- `KERNEL32!HeapAlloc` at `0x1800395e4`
- `KERNEL32!GetProcessHeap` at `0x180039599`
- `KERNEL32!GetProcessHeap` at `0x1800395cf`
- `KERNEL32!GetProcessHeap` at `0x1800396c6`
- `KERNEL32!GetProcessHeap` at `0x1800396ed`
- `KERNEL32!GetProcessHeap` at `0x180039599`
- `KERNEL32!GetProcessHeap` at `0x1800395cf`
- `KERNEL32!GetProcessHeap` at `0x1800396c6`
- `KERNEL32!GetProcessHeap` at `0x1800396ed`
- `KERNEL32!HeapFree` at `0x1800396da`
- `KERNEL32!HeapFree` at `0x180039701`
- `KERNEL32!HeapFree` at `0x1800396da`
- `KERNEL32!HeapFree` at `0x180039701`
- `KERNEL32!SetLastError` at `0x180039556`
- `KERNEL32!SetLastError` at `0x180039556`

## pseudocode

```c

```
