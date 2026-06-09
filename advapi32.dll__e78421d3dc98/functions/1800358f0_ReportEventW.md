# ReportEventW

- ea: `0x1800358f0`
- end: `0x180035ad3`
- name: `ReportEventW`
- size: `483`
- prototype: `BOOL __stdcall(HANDLE hEventLog, WORD wType, WORD wCategory, DWORD dwEventID, PSID lpUserSid, WORD wNumStrings, DWORD dwDataSize, LPCWSTR *lpStrings, LPVOID lpRawData)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180044c20`

## callees

- `0x1800330ac`
- `0x180034890`
- `0x1800358f0`
- `0x180035adc`
- `0x180054a68`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180035971`
- `KERNEL32!HeapAlloc` at `0x18003599c`
- `KERNEL32!HeapAlloc` at `0x180035971`
- `KERNEL32!HeapAlloc` at `0x18003599c`
- `KERNEL32!GetProcessHeap` at `0x180035963`
- `KERNEL32!GetProcessHeap` at `0x18003598d`
- `KERNEL32!GetProcessHeap` at `0x180035a78`
- `KERNEL32!GetProcessHeap` at `0x180035a93`
- `KERNEL32!GetProcessHeap` at `0x180035963`
- `KERNEL32!GetProcessHeap` at `0x18003598d`
- `KERNEL32!GetProcessHeap` at `0x180035a78`
- `KERNEL32!GetProcessHeap` at `0x180035a93`
- `KERNEL32!HeapFree` at `0x180035a86`
- `KERNEL32!HeapFree` at `0x180035aa1`
- `KERNEL32!HeapFree` at `0x180035a86`
- `KERNEL32!HeapFree` at `0x180035aa1`
- `KERNEL32!SetLastError` at `0x180035926`
- `KERNEL32!SetLastError` at `0x180035926`

## pseudocode

```c

```
