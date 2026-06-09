# CHTMLPopup::CalcValidPopupRect(tagRECT &,CDoc *,bool,bool)

- ea: `0x1809d8750`
- end: `0x1809d8ba7`
- name: `?CalcValidPopupRect@CHTMLPopup@@AEBAIAEAUtagRECT@@PEAVCDoc@@_N2@Z`
- size: `1111`
- prototype: `unsigned int __usercall@<eax>(CHTMLPopup *__hidden this@<rcx>, struct tagRECT *@<rdx>, struct CDoc *@<r8>, bool@<r9b>, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1809d9f50`
- `0x1809da8f4`

## callees

- `0x18030035c`
- `0x180373368`
- `0x1807292f4`
- `0x18084ae80`
- `0x1809d8750`
- `0x1809d95cc`
- `0x1810c2cb6`
- `0x1810c2d60`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1809d888a`
- `KERNEL32!CompareStringW` at `0x1809d888a`
- `USER32!GetParent` at `0x1809d88a7`
- `USER32!GetParent` at `0x1809d88a7`
- `USER32!GetWindowThreadProcessId` at `0x1809d87dd`
- `USER32!GetWindowThreadProcessId` at `0x1809d88b5`
- `USER32!GetWindowThreadProcessId` at `0x1809d87dd`
- `USER32!GetWindowThreadProcessId` at `0x1809d88b5`
- `USER32!GetClassNameW` at `0x1809d8802`
- `USER32!GetClassNameW` at `0x1809d8802`
- `USER32!GetDesktopWindow` at `0x1809d8aba`
- `USER32!GetDesktopWindow` at `0x1809d8aba`
- `USER32!GetWindowRect` at `0x1809d88d4`
- `USER32!GetWindowRect` at `0x1809d8ac8`
- `USER32!GetWindowRect` at `0x1809d88d4`
- `USER32!GetWindowRect` at `0x1809d8ac8`
- `USER32!IntersectRect` at `0x1809d88e9`
- `USER32!IntersectRect` at `0x1809d88e9`
- `USER32!GetMonitorInfoW` at `0x1809d8aa0`
- `USER32!GetMonitorInfoW` at `0x1809d8aa0`
- `USER32!MonitorFromPoint` at `0x1809d8a71`
- `USER32!MonitorFromPoint` at `0x1809d8a71`

## pseudocode

```c

```
