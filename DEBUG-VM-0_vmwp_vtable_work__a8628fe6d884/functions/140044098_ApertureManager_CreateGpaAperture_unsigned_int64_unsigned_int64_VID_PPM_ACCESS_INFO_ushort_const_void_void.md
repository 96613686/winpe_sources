# ApertureManager::CreateGpaAperture(unsigned __int64,unsigned __int64,_VID_PPM_ACCESS_INFO *,ushort const *,void * &,void * &)

- ea: `0x140044098`
- end: `0x140044213`
- name: `?CreateGpaAperture@ApertureManager@@QEAAJ_K0PEAT_VID_PPM_ACCESS_INFO@@PEBGAEAPEAX3@Z`
- size: `379`
- prototype: `__int64 __fastcall(ApertureManager *this, __int64, __int64, union _VID_PPM_ACCESS_INFO *, const unsigned __int16 *, void **, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14002088c`
- `0x1400c8be0`
- `0x1400dfc50`

## callees

- `0x140044098`
- `0x14004421c`
- `0x140044240`
- `0x140132940`
- `0x140132d30`
- `0x140172a7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140044126`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140044126`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044194`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044205`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044194`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400440fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400440fb`
- `vid!VidUnmapGpaPageRange` at `0x1400441d7`
- `vid!VidUnmapGpaPageRange` at `0x1400441d7`
- `vid!VidMapGpaPageRange` at `0x1400440eb`
- `vid!VidMapGpaPageRange` at `0x1400440eb`

## pseudocode

```c

```
