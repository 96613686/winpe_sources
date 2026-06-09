# MemoryManager::CreateAperture(void *,unsigned __int64,unsigned __int64,_VID_PPM_ACCESS_INFO *,void * &,void * &,ushort const *)

- ea: `0x140044270`
- end: `0x140044491`
- name: `?CreateAperture@MemoryManager@@UEAAJPEAX_K1PEAT_VID_PPM_ACCESS_INFO@@AEAPEAX3PEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(MemoryManager *this, void *, __int64, __int64, union _VID_PPM_ACCESS_INFO *, void **, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140042240`
- `0x140044270`
- `0x1400549dc`
- `0x140078c98`
- `0x14009f9ec`
- `0x140132940`
- `0x140132d30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400442cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400442cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044375`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400443a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400443a2`
- `vid!VidMapMemoryBlockPageRangeEx` at `0x140044312`
- `vid!VidMapMemoryBlockPageRangeEx` at `0x140044312`
- `vid!VidUnmapMemoryBlockPageRange` at `0x14004447b`
- `vid!VidUnmapMemoryBlockPageRange` at `0x14004447b`

## pseudocode

```c

```
