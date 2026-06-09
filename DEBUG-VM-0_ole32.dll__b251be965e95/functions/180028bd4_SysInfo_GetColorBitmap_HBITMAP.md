# SysInfo::GetColorBitmap(HBITMAP__ * *)

- ea: `0x180028bd4`
- end: `0x180028c73`
- name: `?GetColorBitmap@SysInfo@@QEAAJPEAPEAUHBITMAP__@@@Z`
- size: `159`
- prototype: `HRESULT __fastcall(SysInfo *this, HBITMAP__ **phbmpColor)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180026e78`
- `0x1800b0644`

## callees

- `0x180028bd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028c57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028c57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc9e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028bfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028bfe`
- `GDI32!CreateCompatibleBitmap` at `0x180028c27`
- `GDI32!CreateCompatibleBitmap` at `0x180028c27`
- `USER32!ReleaseDC` at `0x180028c36`
- `USER32!ReleaseDC` at `0x180028c36`
- `USER32!GetDC` at `0x180028c10`
- `USER32!GetDC` at `0x180028c10`

## pseudocode

```c

```
