# MemoryManager::DecommitMemory(_VID_PAGE_RANGE *,uint,unsigned __int64 *)

- ea: `0x140206690`
- end: `0x140206951`
- name: `?DecommitMemory@MemoryManager@@UEAAJPEAT_VID_PAGE_RANGE@@IPEA_K@Z`
- size: `705`
- prototype: `__int64 __fastcall(MemoryManager *__hidden this, union _VID_PAGE_RANGE *, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400dfdc8`

## callees

- `0x14002ebe0`
- `0x14003edc0`
- `0x140042240`
- `0x1400549dc`
- `0x140054af0`
- `0x1400dff70`
- `0x140132940`
- `0x140206690`
- `0x140206960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140206739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140206739`
- `vid!VidDmSlpDisable` at `0x140206921`
- `vid!VidDmSlpDisable` at `0x140206921`
- `vid!VidDmBalloon` at `0x140206722`
- `vid!VidDmBalloon` at `0x140206722`

## string_xrefs

- `0x1402067a5`: `hr == ERROR_VID_VTL_ACCESS_DENIED`

## pseudocode

```c

```
