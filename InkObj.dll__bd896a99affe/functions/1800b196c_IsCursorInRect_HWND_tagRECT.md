# _IsCursorInRect(HWND__ *,tagRECT)

- ea: `0x1800b196c`
- end: `0x1800b1a23`
- name: `?_IsCursorInRect@@YA_NPEAUHWND__@@UtagRECT@@@Z`
- size: `183`
- prototype: `bool __fastcall(HWND hWndTo, struct tagRECT *__struct_ptr)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800589e0`
- `0x1800add38`
- `0x1800dc764`

## callees

- `0x1800b196c`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b19d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b19d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b19ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b19ea`
- `USER32!IsRectEmpty` at `0x1800b199b`
- `USER32!IsRectEmpty` at `0x1800b199b`
- `USER32!GetCursorPos` at `0x1800b19bb`
- `USER32!GetCursorPos` at `0x1800b19bb`
- `USER32!GetWindowRect` at `0x1800b19c9`
- `USER32!GetWindowRect` at `0x1800b19c9`
- `USER32!PtInRect` at `0x1800b19fa`
- `USER32!PtInRect` at `0x1800b19fa`
- `USER32!MapWindowPoints` at `0x1800b19e4`
- `USER32!MapWindowPoints` at `0x1800b19e4`

## pseudocode

```c

```
