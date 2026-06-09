# ReportEventA

- ea: `0x1800610d0`
- end: `0x180061355`
- name: `ReportEventA`
- size: `645`
- prototype: `BOOL __stdcall(HANDLE hEventLog, WORD wType, WORD wCategory, DWORD dwEventID, PSID lpUserSid, WORD wNumStrings, DWORD dwDataSize, LPCSTR *lpStrings, LPVOID lpRawData)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x180039740`
- `0x1800607b0`
- `0x1800610d0`
- `0x18006245c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18006115e`
- `KERNEL32!HeapAlloc` at `0x18006119e`
- `KERNEL32!HeapAlloc` at `0x18006115e`
- `KERNEL32!HeapAlloc` at `0x18006119e`
- `KERNEL32!GetProcessHeap` at `0x18006114a`
- `KERNEL32!GetProcessHeap` at `0x180061189`
- `KERNEL32!GetProcessHeap` at `0x1800612d8`
- `KERNEL32!GetProcessHeap` at `0x180061300`
- `KERNEL32!GetProcessHeap` at `0x18006114a`
- `KERNEL32!GetProcessHeap` at `0x180061189`
- `KERNEL32!GetProcessHeap` at `0x1800612d8`
- `KERNEL32!GetProcessHeap` at `0x180061300`
- `KERNEL32!HeapFree` at `0x1800612ec`
- `KERNEL32!HeapFree` at `0x180061314`
- `KERNEL32!HeapFree` at `0x1800612ec`
- `KERNEL32!HeapFree` at `0x180061314`
- `KERNEL32!SetLastError` at `0x180061110`
- `KERNEL32!SetLastError` at `0x180061110`

## pseudocode

```c

```
